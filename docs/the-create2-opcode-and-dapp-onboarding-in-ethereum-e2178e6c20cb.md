# 以太坊中的 CREATE2 操作码和 DApp 入门

> 原文：<https://medium.com/hackernoon/the-create2-opcode-and-dapp-onboarding-in-ethereum-e2178e6c20cb>

![](img/b0e5e3b131516919b46b768da38e00bc.png)

以太坊网络的下一个重大升级是[君士坦丁堡升级](https://blog.ethereum.org/2019/01/11/ethereum-constantinople-upgrade-announcement/)(原定于 1 月 16 日，但后来被推迟了)。此次升级引入了几个新特性，其中一个表面上看起来并不令人兴奋，但却为可伸缩性和用户加入提供了一系列可能性。这个特性为以太坊虚拟机引入了一个新的操作码:CREATE2。本文将简要概述 CREATE2 的功能，以及它如何显著改善分散式应用程序的采用周期。

# 什么是 CREATE2？

CREATE2 的重要之处在于，它允许 DApp(分散式应用程序)开发人员生成契约地址，而无需实际部署契约。以前，如果不部署合同地址，就无法“保留”它。我们稍后将讨论为什么这是一个采用问题。

实际的 CREATE2 操作码实际上与当前的 CREATE 操作码行为相同，只有一点小小的变化。两者都试图将一些 EVM 字节码作为新契约进行部署。然而，虽然 CREATE 调用部署到的协定地址仅依赖于发送方和 nonce，但是 CREATE2 的新协定地址依赖于额外的输入数据。

简而言之，您可以将它视为允许开发人员对生成的新合同地址进行一定程度的“控制”。

# 创建前的入职流程 2

想一想我们正在努力制造并向大众推销的 DApp。在用户与我们的 DApp 互动的过程中，我们可能会给他们一些链上奖励；可能是以太，令牌，或一些不可替代的令牌。当然，要做到这一点，用户需要自己的地址，尽管这是他们第一次与以太坊[区块链](https://hackernoon.com/tagged/blockchain)互动。

这里有几个选择。

我们可以在 DApp 后台的某个中央服务器上维护一个私钥列表。这将允许我们以低廉的价格向所有用户分发新地址。然而，这对于我们来说是一个重大的[安全](https://hackernoon.com/tagged/security)负担，并且确实把“DApp”的“D”去掉了。

另一个选择是为每个新用户创建一个类似钱包的合同。最初，我们的 DApp 将对本合同的所有操作拥有完全的权利。用户仍然可以收到他们需要的任何东西，无论何时他们*创建了他们自己的以太坊地址，我们都可以很容易地将全部所有权转让给他们，取消我们 DApp 的权利。理论上，这很有效。实际上，它非常昂贵。合同部署需要花费天然气，作为 DApp 的开发者，我们必须不断地为新合同的创建提供资金，即使用户再也不会回来。沉没成本。*

如果我们能够知道这些合同地址而不必花费精力去创建它们就好了！

# **输入 CREATE2**

有了 CREATE2，我们的 DApps *现在可以在合同创建之前知道它的地址。在上面的案例中，我们可以轻松地为所有用户生成钱包合同地址。链外。免费的。*

我们可以将所有需要的代币和游戏中的物品发送到这个地址，当用户准备好提交和要求他们的新财产时，我们可以要求他们将少量乙醚发送到合同地址。这将允许我们的 DApp 去创建合同*免费*，采取一些资金来支付天然气费用！

# 结束的

这只是一个可能的头脑风暴工作流程，但希望给你一个想法，当我们能够为当前未识别的用户保留合同地址时，我们可以开始做什么样的事情。

如果你有什么想法，或者这个高层次的解释有什么可以改进的地方，请告诉我。

在推特上找到我:[https://twitter.com/codingupastorm](https://twitter.com/codingupastorm)