# AWS SDK 到底有多贵？

> 原文：<https://medium.com/hackernoon/just-how-expensive-is-the-full-aws-sdk-abc73d28f62b>

*如果你不熟悉冷启动在 AWS Lambda 环境下的工作方式，那么先读读* [*这篇文章*](https://theburningmonk.com/2018/01/im-afraid-youre-thinking-about-aws-lambda-cold-starts-all-wrong/) *。*

当 Node.js Lambda 函数冷启动时，会发生许多事情:

*   Lambda 服务必须找到一个有足够容量来托管新容器的服务器
*   新容器被初始化
*   Node.js 运行时已初始化
*   您的处理程序模块被初始化，这包括初始化您在处理程序函数外部声明的任何全局变量和函数

如果您为 Lambda 函数启用主动跟踪，您将能够看到在 X 射线中这些步骤上花费了多少时间。不幸的是，初始化容器和 Node.js 运行时所花费的时间没有被记录为片段。但是你可以从持续时间的差异中计算出来。

这里，`Initialization`是指初始化处理程序模块所需的时间。

![](img/c3c11410ea1f7148ff1be812a2cfe4d5.png)

上面的跟踪是针对下面的函数的，它只需要 AWS SDK。如你所见，这个简单的`require`为冷启动增加了 147ms。

```
const AWS = require('aws-sdk')
module.exports.handler = async () => {
}
```

当您的功能需要与 AWS 资源交互时，请考虑这种业务成本。但是，如果您只需要与一个服务(例如 DynamoDB)进行交互，您可以使用这个一行程序节省一些初始化时间。

```
const DynamoDB = require('aws-sdk/clients/dynamodb')
const documentClient = new DynamoDB.DocumentClient()
```

它直接需要 DynamoDB 客户端，无需初始化整个 AWS SDK。我做了一个实验，看看这个简单的改变可以节省多少冷启动时间。

*我的同事* [***贾斯汀·卡尔迪科特***](https://www.linkedin.com/in/justin-caldicott-96b36a9/) *激起了我的兴趣并做了大量的初步分析，这是我的功劳。*

除了 AWS SDK 之外，我们还经常需要 XRay SDK，并使用它来自动检测 AWS SDK。不幸的是，`aws-xray-sdk`包裹里还有一些我们不需要的额外行李。默认情况下，它支持 Express.js 应用程序、MySQL 和 Postgres。如果你只对 AWS SDK 和`http` / `https`模块感兴趣，那么你只需要`aws-xray-sdk-core`。

![](img/4ff5df0df0fc06bf2bb44adb635bd678.png)

# 方法学

我测试了许多配置:

*   [没有 AWS SDK](https://github.com/theburningmonk/aws-sdk-coldstart-overhead/blob/master/functions/no-aws-sdk.js)
*   [仅需要 DynamoDB 客户端](https://github.com/theburningmonk/aws-sdk-coldstart-overhead/blob/master/functions/dynamodb-only.js)
*   [需要完整的 AWS SDK](https://github.com/theburningmonk/aws-sdk-coldstart-overhead/blob/master/functions/aws-sdk.js)
*   [仅需要 x 射线 SDK(无 AWS SDK)](https://github.com/theburningmonk/aws-sdk-coldstart-overhead/blob/master/functions/aws-xray-sdk-require-only.js)
*   [需要 x 射线软件开发工具包并安装 AWS 软件开发工具包](https://github.com/theburningmonk/aws-sdk-coldstart-overhead/blob/master/functions/aws-xray-sdk.js)
*   [需要 x 射线 SDK 内核并安装 AWS SDK](https://github.com/theburningmonk/aws-sdk-coldstart-overhead/blob/master/functions/aws-xray-sdk-core.js)
*   [需要 XRay SDK 内核，并且仅使用 DynamoDB 客户端](https://github.com/theburningmonk/aws-sdk-coldstart-overhead/blob/master/functions/trace-dynamodb-only.js)

这些功能都可以通过 x 光追踪。采样率设置为 100%，这样我们就不会错过任何东西。我们只对**初始化**段的持续时间感兴趣，因为它对应于初始化这些依赖项的时间。

![](img/f56bd3dfbb7e40c6c8e57beee0f3f8dd.png)

`no AWS SDK`案例是我们的对照组。我们可以看到每个额外的依赖增加了我们的`Initialization`持续时间多少时间。

为了收集具有统计意义的样本数据集，我决定使用阶跃函数来自动化这个过程。

![](img/2299a02eaabf6f31f1d2c22d40f6f1be.png)

*   状态机接受一个输入`{ functionName, count }`。
*   `SetStartTime`步骤将当前的 UTC 时间戳添加到执行状态中。这是必要的，因为我们需要实验的开始时间来从 X 射线中提取相关的痕迹。
*   `Loop`步骤触发指定功能所需的冷启动次数。为了触发冷启动，我在调用函数之前以编程方式更新了一个环境变量。这样，我保证每次调用都是冷启动。

![](img/0378af707c6963d72434b044aebffa40.png)

*   `Wait30Seconds`步骤确保在我们试图分析它们之前，所有的轨迹都被发布到 x 射线。
*   `Analyze`步骤获取 XRay 中所有相关的轨迹，并在`Initialization`期间输出几个统计数据。

每种配置都经过 1000 多次冷启动测试。偶尔 x 射线痕迹是不完整的(见下文)。这些不完整的轨迹在`Analyze`步骤中被排除。

![](img/3e375ff6e5e6cd70db2fa45f69cf6eaf.png)

where is the AWS::Lambda:Function segment?

每个配置也用 WebPack 测试过(使用[无服务器 webpack](https://github.com/serverless-heaven/serverless-webpack) 插件)。*感谢*[*Erez Rokah*](https://medium.com/u/d7e408123f72?source=post_page-----abc73d28f62b--------------------------------)*的建议。*

# 结果呢

这些是所有测试用例的`Initialization`时间。

![](img/528910950b22fcd13c315e3a76ea7ca1.png)![](img/3523ecb5e90738123ea40216c809fffc.png)

主要观察结果:

*   WebPack 全面提高了`Initialization`时间。
*   在没有任何依赖的情况下，`Initialization`在没有 WebPack 的情况下，平均时间仅为 1.72 毫秒，在有 WebPack 的情况下，平均时间为 0.97 毫秒。
*   添加 AWS SDK 作为唯一的依赖项，在没有 WebPack 的情况下平均会增加 245 毫秒。这是相当重要的。添加 WebPack 也没有明显的改善。
*   只需要 DynamoDB 客户机(前面讨论过的一行代码变化)就可以节省 176 毫秒！在 90%的情况下，节省时间超过 130 毫秒。有了 WebPack，节省的成本更是惊人。
*   需要 XRay SDK 的成本大约与 AWS SDK 相同。
*   在使用完整的 x 射线 SDK 和 x 射线 SDK 核心之间没有显著的统计差异。有或没有 WebPack。

![](img/cb78dea9f896001dc14239cfecb910e8.png)

嗨，我的名字是崔琰。我是一个 [**AWS 无服务器英雄**](https://aws.amazon.com/developer/community/heroes/yan-cui/?source=post_page---------------------------) 和 [**量产无服务器**](https://bit.ly/production-ready-serverless?source=post_page---------------------------) 的作者。

您是否正在为无服务器而苦恼，或者需要最佳实践方面的指导？您希望有人审查您的架构并帮助您避免代价高昂的错误吗？别担心，我是来帮忙的。 [**我们谈谈吧！**](https://theburningmonk.com/hire-me/)

如果你喜欢这篇文章，为什么不跟随我并获得更多呢？

我也很感激你对帕特里翁的支持。作为回报，你可以通过私人 Slack 频道和 1-2-1 辅导从我这里获得直接帮助。

[![](img/cfe17cc5258f57f589af06648f7955c6.png)](https://www.patreon.com/bePatron?u=905909)![](img/5a59be5d40425e9e80791bc6ba83f2b6.png)

查看我的新课程，[**AWS 步骤功能完整指南**](https://theburningmonk.thinkific.com/courses/complete-guide-to-aws-step-functions?source=post_page---------------------------) 。

在本课程中，我们将介绍有效使用 AWS Step Functions 服务所需了解的一切。包括基本概念、HTTP 和事件触发器、活动、设计模式和最佳实践。

在此获取您的副本[。](https://theburningmonk.thinkific.com/courses/complete-guide-to-aws-step-functions?source=post_page---------------------------)

![](img/6487f5bfe99e95b5e57f2206002c9696.png)

来了解 AWS Lambda: CI/CD 的操作性**最佳实践**，本地测试&调试功能、日志记录、监控、分布式跟踪、金丝雀部署、配置管理、认证&授权、VPC、安全性、错误处理等等。

代码 **ytcui** 还可以获得**票面价格 6 折**。

[获取您的副本](https://bit.ly/production-ready-serverless)

*原载于 2019 年 3 月 23 日*[*https://theburningmonk.com*](https://theburningmonk.com/2019/03/just-how-expensive-is-the-full-aws-sdk/)*。*