# Token 地下 0x3: WTF 是潘瓦拉捐赠平台？

> 原文：<https://medium.com/hackernoon/token-underground-0x3-wtf-is-the-panvala-donation-platform-91cef466eaab>

*瓦西里·苏马诺夫和奥利娅·格林*

![](img/dc37ab893ffa1779c176e202de45eb32.png)

*我们深入到* [*Panvala*](https://www.panvala.com/) *平台，为 Panvala 团队和整个区块链社区奠定了现有令牌模型的一些痛点。渴望参与进一步的讨论并获得反馈。*

我们的 TU 会议 0x3 从这里开始。这次我们关注的是 Panvala，这是一个由 Consensys 构建的捐赠平台，它有一个内在的 PAN 令牌和一个用于资助的智能合同概念，称为“令牌电容器”。它是新奇的、有前途的东西，还是仅仅是围绕一个平庸概念的华丽辞藻的火花？让我们开始吧。

**确定目标和系统参与者**

和往常一样，我们从识别系统目标和应用领域开始。以下是来自 Panvala 网站的引文:

> Panvala 是一个捐赠驱动的平台，帮助资助整个以太坊社区所依赖的工作，通常是促进以太坊的安全性或可扩展性的工作。我们的捐助者向一个名为令牌电容器的智能合同提供资金。每个季度，我们的代币持有者使用代币投票决定哪些资助申请应该由代币电容器资助。

因此，Panvala 是一个开发出来的系统，其目的是为重要的资助提案提供公平的资金，使以太坊在安全性方面做得更好。

系统参与者包括:

*   **捐赠者。**该角色归结为提供将用于资助拨款提案的资本。
*   **被资助人。**从系统获得资金以完成授权提案的社区成员。
*   **治理的参与者。**治理旨在提供一种对资金分配做出集体决策的方法。这个角色可以由任何 PAN 令牌持有者来执行。

**实施什么机制来实现系统目标？**

为了实现公平资助对整个生态系统真正重要的提案的目标，他们需要解决两个主要任务:

1.  以透明、安全和可靠的方式筹集和分配资金。
2.  建立允许公平分配这些资金的机制。很明显，如果关于资金分配的决策是在集中模式下做出的，这些决策将涉及个人偏好。这为腐败和企业战争打开了巨大的可能性(例如，一个团队可以贿赂决策者，以阻止他们的竞争对手获得资金)。

为了解决第一个任务，Panvala 团队提出了“令牌电容器”的概念。

**令牌电容**

这是一个智能合同，从捐赠者那里收集令牌流，并根据投票结果将它们分配给选定的赠款申请(投票程序将进一步详细描述)。该系统的工作原理如下:

![](img/79829793f30c7e327f7bde78bdc067d3.png)

令牌电容器的概念可以被称为具有两个阀门的浴缸:一个给浴缸注水，而另一个放水。相当简单的系统。但是，让我们更仔细地看看。

代币电容器与 PAN 代币一起操作，作为支付手段。在 2019 年找到这样的方法难道不令人惊讶吗，因为已经有像戴这样稳定的公司可以作为一个稳定和成熟的支付解决方案。

令牌电容器的描述包括短语“设计用于充电”“充值”的意思是捐助者将基本上向该合同发送 PAN 令牌，以资助未来的赠款提案。但是，要发送东西，你首先需要得到它。

该小组考虑的默认情况是，捐赠者从以前接受过赠款的受赠者那里购买代币。看起来不太有说服力:捐赠者购买代币，受赠者出售代币有什么意义？显然，他们需要一些通用的支付工具，至少是 DAI 或 ETH，这些工具可以在社区中轻松用于支付，或者在必要时无缝转换为法定货币。

除了不必要的行动之外，受资助者面临的另一大威胁是什么呢:PAN 代币非常不稳定，因此他们最终获得的实际金额可能会大大低于发放时的初始金额。

> 因此，他们被激励尽快出售这些代币，他们最好领先于其他可能做同样事情的团队。

这里的主要问题是，潘没有任何持续的需求:所有购买这种令牌的行为都与“捐助者的慈善”有关，或者与向这一系统捐款的人的善意有关。因此，在 PAN 代币从代币电容器释放后的短时间内，受让人之间的资金分配后的供给可能相当高，而需求可能很低。

> 这将导致 PAN 代币的高波动性(除非 Panvala 团队将在做市方面进行大量投资)，这将使受让人处于复杂的境地。

**治理**

第二个任务被定义为“建立一个允许公平分配这些资金的机制”，这显然可以归结为治理过程的设计。以下是[关于潘瓦拉 alpha 版本的博文](https://media.consensys.net/panvala-releases-alpha-mvp-with-slate-governance-model-fe7679a022fe):

> 在采用 slate 治理作为我们的模型之前，Panvala 最初是作为一个更传统的令牌管理的注册中心构建的。Slate 治理是令牌管理的注册中心的替代方案。候选人治理允许我们平台上的个人或组织策划一系列提案(注册中心)，并让该候选人与平台上的其他候选人竞争令牌持有者的支持。Slate 治理更类似于投票系统中的表示，并解决了注册中心中存在的每个提案的投票者知识不足的问题。

在我们看来，所提出的方法非常有趣，并且可能比普通的 TCR 更好。候选人之间的竞争，或者一组拨款提案，是一个好主意，允许代币持有者在所有拨款提案之间“分散”他的投票，而不是在单一提案上下注。不错，可以用。

**赌注游戏**

该项目的团队提出了一个额外的令牌使用场景——赌注游戏——或智能合同审计系统，该系统要求提交令牌作为概念的核心部分。这意味着，任何想审核这份合同并获得 A 的人，都必须拿出一定数量的代币来证明他们的代码不是废话。

这不是一个坏主意，但是有一个问题——为什么不使用 ETH 或 DAI？它可以激励审计人员更深入地挖掘智能合同问题，因为如果他们发现安全错误，他们会得到奖励。此外，这里有一个公开的问题——谁是法官？

> 我们如何知道代码中是否有真正的错误，或者只是审计人员的另一个幻想？

**进一步的想法**

对“令牌电容器”及其治理设计的再思考。首先，不清楚哪些代币可以用于投票。例如，如果我是一个捐赠者，我想资助一些提案，我将需要执行这两个功能——将我的令牌捐赠给令牌电容器和参与治理。

因此，澄清已经授予令牌电容器但尚未分发的令牌是很重要的——以前的所有者是否拥有这些投票权？如果没有，捐赠者将不得不购买一批代币:一个用于捐赠，另一个用于持有以便能够投票。这种方法似乎不方便，也没有经济效益。

此外，还可能有另一个副作用:捐赠的代币对于所有者来说永远失去了，而代币电容器外持有的代币可以多次用于参与投票和确定授权提案的命运。似乎持有代币在经济上是理性的(至少持有人手中积累了一些权力)，而捐赠更像是慈善活动。

> 因此，投票的代币持有者比捐款者多的情况是很有可能的。

总而言之，石板治理非常有趣，因为健康的竞争总是促进进步。

但是，可能会有一些攻击，如创建许多类似的赌注，使部分选票在他们之间分配，并简化特定令牌持有者群体批准他们感兴趣的候选人的任务。

这个问题源于这样的问题:“谁以及为什么能够创建新的石板？这样做需要满足什么条件？该系统如何防止石板复制？”

**我们对团队的看法和想法**

“令牌电容”的想法总体来说还不错，但目前执行起来并不理想。用于价值转移的 PAN 令牌使这一系统变得薄弱，对捐助者和受赠者都不方便，因此引起了关注。

**想法:**运行一个单独版本的令牌电容器，只能用戴来填充，并使用 PAN 令牌来管理它。这部分资金可以在投票者中分配，用于得到完美执行的拨款提案，就像某种治理费一样。

但这里有一个问题，如何识别赠款执行的优秀。与占卜预测市场整合如何？开个玩笑，因为与市场相关的赠款似乎相当缺乏流动性，除了最重要和已知的那些。

候选人治理机制是一种有趣的方法，但是还需要团队澄清候选人创建的条件和确切的投票程序。

**想法:**定义透明的规则，规范令牌持有者参与治理。我们建议允许已经向令牌电容器捐赠令牌的令牌持有者(尽管 PAN 作为价值转移实际上是不好的)根据其尚未分发的令牌持有量参与治理。

> 这里有一个问题—我们如何选择在下一轮分发谁的令牌？我们认为某种随机力学可以解决这个问题。

**赌注游戏。**当然，我们知道团队总是在寻找一些想法来扩展他们[通常无用的]令牌的效用。在我们看来，用潘做智能合同审计的筹码实在是一个笑话。这没有任何经济意义:代币可以被任何其他代币代替，只要这些代币可以作为审计员的奖励而获得。

此外，“法官的法官”问题对于这场“赌注游戏”来说也非常紧迫。现在，承认合同为“安全”或“不安全”的确切条件还不清楚。

**创意:**为申请人选择免费的股份代币进行审核。如果申请人提交了一份申请，其中一些狗屎令牌被用于股权，没有人会进行审核。让市场成为选择股权代币的主要监管者。

此外，这是项目路线图中的两个要点。未来，他们计划实施一些新功能，包括:

> *平台* ***治理名单*** *创建，赋予令牌持有者对治理参数的控制权*
> 
> ***立桩*** *为围绕板岩固化创造必要的经济激励*

这很有趣，但是需要更多的信息才能得出这样的结论——考虑了哪些治理参数？为什么参数正是这些，而不是其他的？他们能接受什么样的价值观？我们对定位功能有同样的疑问。

> 实施股权是为了什么目的？确切的机制是什么，赌注理念背后的经济学是什么？

总而言之，Panvala 捐赠系统的想法和承诺是非常酷的，并且在以太坊生态系统中非常需要，以促进其可持续发展。

但是，在我们看来，这个想法的执行目前并不理想，而且在经济方面有一些紧迫的问题。

*本文由 Technomads 撰写:Vasily Sumanov 和 Olga Grinina。关于 web3 和后工业经济的更酷的东西或与我们聊天你可以在我们的*[*Twitter*](https://twitter.com/nomad_notes)*上。*