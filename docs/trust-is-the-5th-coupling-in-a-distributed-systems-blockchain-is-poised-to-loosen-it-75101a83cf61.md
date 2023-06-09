# 信任是分布式系统中的第五个耦合:区块链正准备放松它

> 原文：<https://medium.com/hackernoon/trust-is-the-5th-coupling-in-a-distributed-systems-blockchain-is-poised-to-loosen-it-75101a83cf61>

弗兰克·莱曼&斯里纳斯·佩雷拉 

![](img/623f0d43535adff8dd01005837307817.png)

# 耦合的四个方面

我们建立的系统会改变。一个正在使用的系统会经历变化以跟上世界的变化。架构的主要目标是构建简化这一变化过程的系统。

为了缓解这种变化，我们分而治之。我们将系统分解成松散耦合的部分，这样我们就可以尽可能独立地开发、分析、理解和更改每个部分。模块、功能、对象、组件、服务和微服务是将系统分成这些独立部分的努力的例子。

我们希望减少耦合，将系统分解成多个部分。然而，不同的部分必须一起工作。因此，完全解耦一个系统是不可能的。所以我们努力争取松耦合。其程度是根据自主的四个方面来衡量的(自主越多越好):

1.  **时间自主**——它允许选民在不可预知的时间点做出反应。例如，因为一个成分意识到变化的工作负荷；或者它崩溃并且必须恢复，等等。等等。
2.  **引用自治** —请求不会发送给特定的成员。例如，因为几个组件实现重叠的功能；或者因为安装了成分的新版本等。等等。
3.  **格式自治** —它允许信息发送者和信息接收者不必事先就信息的确切语法达成一致。例如，因为不同版本的发送者或接收者产生或期望不同种类的信息；或者因为使用了不同的信息表示法(CSV vs JSON 等等)
4.  **平台自主性** —它允许基于非常不同的技术实现交互的组成部分。例如，因为组件是在不同的时间点开发的，当时技术是流行的；或者这些成分是基于最适合其用途的技术开发的，等等。

在这篇文章中，我们认为信任也可以被认为是另一种形式的耦合，耦合的第五个方面。

# 理解信任

分布式系统的成员通过潜在的不可信网络进行通信。因此，每个这样的通信都是不可信的。通信可能发生在信任建立之前:一旦从另一个参与者接收到消息，每个参与者可以决定是否信任某一方。每个参与者之间的信任根据需要建立。

什么是“信任”？《牛津词典》将信任定义为“对某人或某事的可靠性、真实性或能力的坚定信念。”在系统中，这是一种坚定的信念，即系统、子系统或系统中的参与者将根据其角色行事。

信任基于经过认证的身份。这种身份是授权的基础；授权是广义的，例如授权从我的账户中扣款并将相应的钱汇给其他人。授权包括强假设，即被授权的主体将根据已建立的规则行事，例如，在资金转移中，借记金额和贷记金额的总和是相同的。

我们的大多数系统通过带外方式建立信任。在某些情况下，设计人员通过使用防火墙来确保系统中的每个人都是可信的。在其他情况下，DevOps 人员配置要使用的凭证。在第二种情况下，并不是每个人都被信任，但是已经建立了一些信任链接。值得注意的是，凭证并不代表建立的信任，而是传递信任的机制。当凭证被共享时，信任被建立。

# 第五耦合

今天的企业集成解决方案假设系统中已经有一组具有正确凭证的参与者。一旦他们进入系统，他们就可以广泛地访问系统，并且他们的信任级别基本保持不变。通过假设这种“可信参与者”,最终的集成解决方案非常灵活:人们可以交换、发展、添加成员，而不必担心信任。因此，我们可以认为信任是松散耦合的一个“隐藏的”自治方面。因为参与者之间的信任已经建立，我们认为他们是耦合的。例如，他们不能在互动过程中改变他们的信任行为。

今天的集成解决方案大多是“封闭的”,因为相互作用的组成部分是预先知道的。因此，信任不是显式的关注，而是隐含的假设(否则就不会向系统中添加成分)。必须明确处理其他自治方面，例如，必须添加一个中介来采用新组件的格式要求。

相反，在一个“开放”的环境中，信任不能是隐含的，它必须明确地包含在内，以支持向系统中添加事先不知道的新成分的灵活性。我们可以设想这样的系统，其中信任关系不是假定的，并且作为操作的一部分，信任被建立。例如，像区块链这样的技术使得实现这样的用例成为可能。使用分散身份，系统可以验证用户的某些属性，作为交易的一部分，而无需人工参与。

# 一个例子

让我们举一个例子。如果你考虑让一家银行成为这个系统的一部分，你需要通过一个注册过程，他们会收集你的信息，得到你的签名，检查你的文件。经过这些检查，如果你通过了，信任就建立了，你就被允许加入这个系统。然而，就软件系统而言，信任是由一个单独的进程建立的，而不是系统。我们认为，在这种情况下，参与者是通过预先建立的信任联系在一起的。耦合通常是昂贵的，因为它们需要复杂的离线过程。

相比之下，使用诸如“区块链可验证声明”之类的系统，该系统可以与不受信任的个人进行交互，并按需建立信任。此外，系统可以基于可能的信任级别提供不同级别的能力。在这种情况下，信任是一个动态的实体，而不是我们系统中预先建立的静态条目。例如，如果参与者错过了一笔贷款的付款，这可能是他的信任级别应该被调整的信号。

然而，值得注意的是，尽管由于其分布式的本质，区块链是构建松散耦合的信任系统的自然选择。类似的想法也可以使用其他手段来实现。例如，系统可以根据用户的行为调整用户的访问级别。

# 结论

总之，我们认为信任也是一个耦合维度。在这方面拥有自主权的系统可以与不受信任的一方合作，并随着时间的推移发展信任。