# 如何用用户故事评估敏捷项目

> 原文：<https://medium.com/hackernoon/estimating-agile-projects-with-user-stories-82f67365a6a2>

![](img/ef74e29267b96942f702260622ea350d.png)

评估软件项目是困难的。在开发过程的早期，您不能精确地定义项目的范围。因为不可避免的是，在开发开始后，范围将会改变，因为到那时团队将会对项目及其上下文有更多的了解。尽管如此，在开始之前，团队必须估计他们项目所需的资源，至少是大概的资源。

那么，你应该如何解决这个问题呢？

传统的方法是进入一个分析阶段，在这个阶段，您创建一个需要构建的详细规范。但是正如我们所说的，在开发开始之前，项目的范围并不明确。因此，分析不是最好的方法。

# 什么是用户故事？

简单而强大的*用户故事*是对需要实现的单一功能的一句话描述。它描述了用户角色、需要执行的功能以及期望的结果。写这些故事是描述我们想要构建的东西的一种灵活方式。

用户故事的伟大之处在于它是用简单的语言写成的。因此，即使您没有软件需求管理或项目管理方面的技术背景或经验，您也可以编写一个，因为您可以描述应用程序的高级需求，而无需钻研技术细节。

从用户的角度来看，用户故事对于获取期望的功能至关重要。他们还帮助您向团队的所有成员传达做出某些决定的内容、方式和原因——即使这个团队只有一个开发人员。通过用简单的语言描述期望，你也可以让非技术团队成员，比如设计师、QA 工程师和客户支持专家，也可以访问这个范围。

# 如何写一个用户故事

一个典型的用户故事遵循以下公式:

作为一个<user role="">，我要<functionality description="">为了</functionality></user>

示例:作为一名*管理员*，我想*创建供应商*，以便能够*向供应商分配订单并查看交易*。

用户是管理员。功能是*创建供应商*——这是管理员需要做的。最后的结果是*向供应商分配订单并查看交易，*这解释了为什么管理员首先需要创建供应商。

很容易将用户故事与您为开发人员编写的任务混淆起来。任务类似于用户故事，但区别在于:任务通常只描述需要做什么，而不提供任何上下文，更多的是关于实现。换句话说，任务描述了为了实现用户故事需要做什么:设计一个屏幕，启动一个后台工作，制作一个可点击的按钮，等等。而故事，则是高层次的，简单的。它们提供了任务的定义和推理。

创建积压的用户故事可能会花费你一些时间。你可能会发现自己处于这样一种情况，你不明白你所设想的某个功能是如何从用户的角度来看待的。这可能是一个信号，表明你需要重新开始。

# 使用故事点进行估计

一旦你写好了你的用户故事，你就可以开始评估它们了。

如果你没有软件开发的经验，这是你需要开发人员做的事情，因为你不知道如何估计某项功能的工作量或持续时间。您可以要求将为您构建应用程序的开发人员提供对用户情景的评估，或者雇用一名顾问，并使用他们的评估作为基线。

您可能倾向于通过估计完成用户故事所需的时间来进行估计。然后，您将能够将 backlog 中所有用户故事的时间加起来，除以从事该项目的开发人员的数量，并计算出完成该项目所需时间的粗略估计。

不幸的是，这种方法行不通——实现总是至少需要和估计的一样多的时间。有时，甚至需要更多。当用户故事花费更多时间时，整个计划就会出错。一些故事依赖于其他故事，这导致了更多的延迟，迫使开发人员一次处理多个故事。结果是，整个估计最终是“关闭”的，项目花费的时间是预期的两到三倍。

因此，我们需要承认软件项目中的高度不确定性。与其估计用户故事的持续时间，不如估计实现它们所需的相对工作量。

好吧，这是最简单的方法:从 1 到 3 给你的用户故事打分。你所做的是对故事的复杂程度进行排序——简单是 1，普通是 2，复杂是 3。对于那些几乎不需要任何努力的故事，比如改变设置或更新设计，你甚至可以给它们打零分。这个没有公式。仅仅使用你的直觉和评估者的经验(或者评估者，如果你有一个团队来定义故事点的话)。

关于故事点最好的部分是它们是相对的。因此，一旦你定义了一个简单的用户故事，你就可以将它与另一个用户故事进行比较，以确定它是同等的、更简单的还是更复杂的。

# 基于故事点测量团队的速度

你可能想知道使用故事点是否有任何意义。毕竟，他们不允许你估计项目或预算的持续时间。

事实上，他们不…至少不是直接的。但是您可以通过测量您的团队在每个 sprint 中完成了多少故事点，将这些对工作量的估计转化为对所需时间的估计。这些测量被称为*团队的速度*。

项目进行得越深入，你就能越好地计算出团队每次冲刺完成的平均故事点数。通过知道 sprint 的持续时间，并将其乘以故事总数除以速度，您可以估计整个项目的持续时间。

简单来说？如果你每次冲刺能完成三个普通故事(2 分)和一个复杂故事(3 分)，那么你需要 34 次冲刺来完成一个包含 300 分的项目。