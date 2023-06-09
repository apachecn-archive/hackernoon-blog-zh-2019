# 区块链 101:共识协议简介

> 原文：<https://medium.com/hackernoon/blockchain-algorithms-101-a-introduction-to-consensus-protocols-c00f884a01fb>

![](img/cf32e41451ed36cbaf3692af2b78fdf8.png)

尼依格罗酒店·马基雅维利曾经说过，“对于人类，我们一般可以说他们是善变的、虚伪的和贪婪的”。这句话是关于在一个充满不可信任的人的世界中航行所必需的不信任，在他的时代和我们的时代都同样适用。

在一个“虚假”的世界里，理解信任的善变本质，并在我们自己之间找到某种程度的共识，以此来看待我们所认为的“真理”，是非常重要的。尽管人类几个世纪以来一直面临的这一挑战在我们这个时代可能无法完全解决，但通过区块链技术带来的创新，我们已经比我们的祖先更加接近了。在区块链的世界中，有 5 个‘主要’(大部分是已知和使用的)共识协议；

1.工作证明

2.股权证明

3.重要证据(PoI)

4.逝去时间的证明(诗人)

5.委托状态证明(DPoS)

尽管自从区块链的最初概念提出以来，已经有许多提议的和理论上一致的算法，但它们大多超出了本文的范围。

在整个区块链生态系统中，最广泛使用和最知名的共识算法是工作证明算法。

这种算法被比特币和以太坊等几乎所有主要货币(在一定程度上)所利用，其工作原理是通过称为矿工的特殊节点确认链交易和创建新块。想象一下，数字 64 写在教室的黑板上。

教室里坐着许多学生，每个人手里拿着 10 个独立的骰子，掷出完美的 64。虽然每个人掷骰子不费什么力气，但任何一个人都要连续掷出许多次才能最终掷出完美的“64”，不管有多少个边的组合加起来可能是 64。

现在想象一下，每一个掷骰子的人都在为某个奖项竞争寻找加起来等于 64 的新的数字组合，并且每当一个竞争者掷出确实加起来等于 64 的某个组合时，没有其他竞争者可以再次提交该组合来获奖，迫使每个竞争者在最终获得获奖的掷骰子之前进行越来越多的尝试。

这种“得票最多者得奖”的工作方式基本上就是 PoW 的工作方式，只不过他们不是试图掷骰子来获得一个加起来等于 64 的独特组合，而是使用计算机来执行称为哈希函数的复杂数学函数，希望找到新的、非常特殊格式的哈希。

为了使工作证明的概念包含三个主要组件，即事务、块和挖掘器——挖掘器连接到附加的组成部分。虽然工作验证算法看起来(通常也是)非常直接和有用，但有许多因素——如其总成本、功耗和安全性(针对一些攻击，如 51%攻击)——淡化了其整体功能。

以比特币挖矿为例；比特币是第一种被发明的加密货币，它利用 PoW 共识算法来促进其连续的交易流，并每 10 分钟创建一个新的区块。由第一个成功解决上述数学函数的矿工创造的每一个区块，都需要无数台极其强大和高度专业化的计算机来创造。

解决后，成功的矿工(或矿工组)将获得总计 12.5 比特币的奖励(截至 2018 年 11 月 18 日，价值 69，962.50 美元)。显然，这一高额报酬吸引了大量极具竞争力的矿工每天 24 小时工作(并消耗大量电力)。因此，比特币网络消耗的电力相当于整个新加坡的电力。

除了工作证明共识算法需要的大量电力之外，随着时间的推移，已经变得很明显的是，通过聚集多个高增长和高电力矿商而创建的大型财团已经转移到专门的地点——例如沙漠，以便利用太阳能，或者苔原，以便自然冷却他们的机器。

由于他们的发展和创造性的能源解决方案，这些团体很快将“业余爱好者-矿工”推向了濒临灭绝的境地，有效地集中了有意分散协议的采矿能力。这种形式的网络“攻击”被称为 51%攻击，随着计算能力的增加和变得更便宜，它正在成为一个巨大的问题。

虽然工作证明仍然是比特币生态系统不可或缺的一部分，但许多其他加密货币——如以太坊——正在试图摆脱这种共识协议，转向利益证明协议。在基于赌注的加密货币证明中，每个连续区块的创建者以两种方式之一选择:

a.通过随机区组选择

b.通过基于硬币的选择

随机化块选择利用一个公式，该公式将链上的最低哈希值(很像工作证明算法的数学函数的结果哈希值)与块的赌注(投入一个黑块的金额)相结合。

> 由于赌注是公开的，每个节点可以预测哪个帐户将赢得伪造新区块的权利。这种类型的选择允许多个参与者来构建块，不排除任何个人参与交易，而不管他们已经向任何一个或多个块投资了多少资金。
> 
> 以这种方式，由利害关系证明算法实现的随机区组选择使得每个参与者/竞争者更加平等。

由于在股权证明算法中不需要复杂的计算工作，所以在股权交易的证明中不涉及矿工。相反，称为验证器的专用节点用于验证事务，并通过专用流程将它们放到链上。验证者是基于他们在他们验证的相应资产中的总财富来选择的，他们接收交易费作为对验证交易的支付，并且一般来说，持有该资产最多的人验证最大量的交易，从而赚取最大量的交易费。

我们将在本文中讨论的第三个协议是重要性证明(PoI)共识算法，它可以被描述为一个经济的构建协议，它基于大帐户平衡和可信度。该协议最初由 NEM 设计和开发，该组织是一个基于区块链的组织，负责发行和利用 XEM 加密货币令牌，根据网络中每个验证者/参与者的可信度评分。

为了获得更高且不断更新的分数，每个参与者不仅必须拥有大量的账户余额，还必须以他们正在促进的加密货币的形式保留通过交易获得的所有资产，并保持他们总余额的至少 10%投资于所述加密货币。

这些规定迫使用户允许评估他/她的可信度，试图在参与者中保持对加密货币整体价值的长期看法。

就像股票市场投资一样，一个人持有的公司股票越多，这个人在整个组织中的权重和权力就越大，一个人对基于加密货币的重要性证明的投资越多，他们的总体可信度得分就越高。

此外，虽然大的利益相关者有很大的影响力，即使那些拥有一个公司股份的人也可以从组织的整体增长中获利，或者在这种情况下，从网络中获利。

一方面，重要性证明算法是有益的，因为它鼓励更多的人参与进来，并开辟了整体财富分配的可能性——因为任何贡献者都可以赚取更多的 XEM。

然而，另一方面，总是较大的参与者具有更大的能力来获得更高的可信度分数，从而获得更多的利润。这种奖励是通过一个称为收获的过程来完成的，通过网络上每个既得节点对新块的分布式计算来实现。

要参与此计算(并成为“既得”节点)，必须拥有相应加密货币的至少 10，000 英镑的既得(或活动)余额。

继续我们在本文开头列出的共识算法的描述，我们现在将继续进行时间流逝协议(PoET)的证明。经过时间的证明，它被设计为一个“公平”的共识模型，关注于效率，并围绕在最大可能数量的网络参与者中的分布式领导者选举的概念。

此外，控制流程(或领导整个流程)的成本总是与从中获得的价值成正比。因此，要控制(或领导)这个链条，就必须投入大量的时间和金钱。最后，链上的所有参与者需要验证领导者是以合法的方式选择的。

PoET 旨在通过使用新的、安全的 CPU 指令来实现这些目标，这些指令在消费类处理器中迅速普及。

通过利用这些新功能，基于 PoET 的硬币确保了领导者选举过程的安全性和随机性，而不需要像工作证明这样的过程所需要的电量或计算能力。

此外，在基于 PoET 的加密货币中，每个验证者向飞地请求等待时间，并且对于交易块具有最短等待时间的验证者被选为领导者。这种方法任意地在整个验证器池中分配领导选举，其分布类似于其他彩票算法。

因此，当选的概率与捐助的资源成正比。然而，参与的低成本增加了验证者池将大于 PoW 或 PoS 共识协议的可能性。因此，使得基于 PoET 的加密货币更加开放，并对公众可用。

尽管耗时一致性算法的证明没有像 PoW 或 PoS 这样的算法那样被广泛地实现或了解，但是它可能拥有巨大的潜力，因为它具有让更多人充当验证者的更广泛的能力。

最后，还必须指出的是，PoET 算法运行在 CPU 上，而不是 GPU 或 ASICs 上，这允许返回计算的“美好旧时光”，许多人都可以参与其中，而不仅仅是那些拥有强大、昂贵硬件的人。

本文将讨论的第五个也是最后一个共识协议是委托利益证明(DPoS)算法。这种协议被认为是前面提到的所有协议中最民主和“公平”的，可以概括为一种环境，在这种环境中，员工(节点)可以解雇他们的老板(领导)，而不是相反。

通过授权的利益相关证明算法，利益相关者批准的权力用于解决共识问题。此外，利益相关者(选出的代表)还决定区块间隔、费用和交易规模限制。

在 DPoS 系统中，利益相关者可以选举任意数量的“见证人”来生成区块。

每个账户允许每个证人每股一票——这个过程被称为批准投票。当利益相关者表达他们想要的证人数量时，他们也必须从总的人才库中投票选出至少同样多的证人。每一次证人制作一个积木，他们都会得到一笔费用，这笔费用也是通过民主投票产生的。通过每天一次计票来更新证人组，允许新证人获得与老证人一样的奖励。

尽管 DPoS 还没有被广泛采用，但是随着越来越多的项目开始意识到它的整体潜力，它正在迅速获得动力。

随着区块链生态系统随着时间的推移继续发展，并在我们经济和整个世界的私营和公共部门中变得越来越重要，新的协议将继续发布，并取代我们今天使用的协议。

虽然目前工作证明和利益证明主导了区块链世界中那些人的想法和实现，但变化的浪潮来得又快又强，许多算法——可能(也很可能)是本文中提到的一些算法——可能会很快超过它们。

虽然这些肯定不是共识算法的全部，但它们是许多新项目和新共识协议的坚实基础。