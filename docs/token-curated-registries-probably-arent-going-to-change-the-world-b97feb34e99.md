# 令牌管理的注册中心可能不会改变世界

> 原文：<https://medium.com/hackernoon/token-curated-registries-probably-arent-going-to-change-the-world-b97feb34e99>

![](img/d9ef3688cc10721f7cae225bc5a22e3e.png)

Think how much easier Santa’s job will be with TCRs to streamline his extensive list operations (Photo by [Mike Arney](https://unsplash.com/@mikearney?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral))

令牌管理的注册中心(TCR)是一个奇怪的概念。本质上，它们是创建列表的一种手段，一个听起来相当平淡无奇的目标。然而，拨开表面，它们是一张激励和博弈论交织的网，可能会引发比它们解决的问题更多的问题。

我不打算深究 TCR 是什么，因为有一个[号](/@ilovebagels/token-curated-registries-1-0-61a232f8dac7)的[好这样的解释者](/@tokencuratedregistry/the-token-curated-registry-whitepaper-bd2fb29299d6)。简而言之，TCR 以这样一种方式将列表、令牌和投票结合在一起，以允许创建管理列表，其中项目被提议并被投票以包含。这个想法是，通过创建一个定制的列表，它将为那些被包括在内的人创造价值。这将看到来自类似领域的其他人希望被包括在内，迫使他们购买列表令牌，以便他们可以提交自己的考虑。那些管理名单的人同样会因为他们的努力而得到奖励。与此同时，消费者从更好的名单中受益，这些名单不受某个实体的影响，投票是透明的，所有人都可以参与。

相反，本文的重点是列出我认为 TCR 存在的所有问题。从上面的总结来看，其中许多应该是显而易见的。虽然我讨论了三个实际的或提议的 TCR 的例子，但我更关注的是整个概念。

# **排行榜？你真的要和我谈名单吗？**

TCR 的性质使它们很难过于兴奋。一份名单？太好了。谁在乎呢。这部分是由于人们给出了非常糟糕的用例。旧金山的咖啡店列表？真的，谁在乎？这些枯燥的例子使得 TCR 的输出难以概念化。

然而，TCR 有一些有趣的用例。一个这样的例子来自于 FOAM Space，它很好地展示了看似平庸的列表如何被用来产生更伟大的东西。

FOAM 旨在提供一个分散的地图，用户可以通过它添加兴趣点。然后可以对这些进行投票，如果通过，则添加到泡沫地图中。本例中的 TCR 由地图上的这些兴趣点表示。

![](img/8d221fb4c329e0ff82599fe74db9646c.png)

FOAM

记住，我认为泡沫是目前提出的 TCR 的一个更好的例子，让我们看看 TCR 带来的一些潜在的积极和消极影响:

![](img/d6f7d045b55562664e4c3c52ea4898bf.png)

我想从一个清晰的例子开始，因为 TCR 有许多不同的提议，但给出的具体例子很少。还有大量不同的 TCR 实现正在进行中，没有一个“TCR”模型可以作为标准。然而，它们具有相同的总体结构，我对 TCR 的许多问题可以归结为四个核心类别:

1.  弱核心命题
2.  激励不一致
3.  有限且应用不佳的用例
4.  令牌模型

# **弱核心命题**

TCR 旨在允许完全不同的各方达成协议。然而，达成一致的信息可以是客观的，也可以是主观的。主观信息带来了许多明显的问题，但即使是客观信息，如泡沫例子中所概述的，也往往难以核实。“不放心。验证”不是抽象的概念。任何人都可以验证位于比特币核心的 T4 区块链 T5。当涉及到 TCRs 时，这一点就失去了，因为总会有信任的因素。人们仍然可以验证记录的数据和进行的交易，但是因为这些交易记录的是区块链以外的对象，所以他们必须相信这是正确的(Oracle 问题)。

比特币让抵制审查的交易成为可能，对于任何稍微熟悉历史或当前全球金融体系的人来说，这显然是一个有用的功能。分散列表很难创造出同样引人注目的故事，至少不需要令牌和区块链。维基百科涵盖的内容范围比任何 TCR 能够解决的都要广，而且做得令人钦佩。有不准确的地方吗？是的。是否受制于人肆意破坏？当然可以。TCRs 解决了这些问题吗？不。我不相信 TCR 是治疗的解决方案，它们的名字就是由此而来的。

![](img/5b0d8bd8bc912254a2333f1733294100.png)

This was going to be all photos of lists but I couldn’t do that to people (Photo by [Jared Rice](https://unsplash.com/@jareddrice?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral))

由于自由市场的竞争，中央集权的实体被鼓励使他们的名单尽可能好和准确。谷歌和苹果将有自己的偏见，但他们的持续成功部分取决于(现任的力量不能被低估)他们保持竞争力和提供用户想要的体验的能力。他们的任何偏见都可能停留在更高的层次，而不是过滤到个人决策，例如，一家咖啡店是否应该比另一家更突出。

TCR 可能没有来自上面的总体偏见，但在较低和个别级别出现问题的可能性更大。然而，平台偏差也可能取决于策展人在人口统计学上的广泛分布。一个以美国/西欧、富裕、白人、男性和中年人为主的用户群——这在许多技术平台上都很常见——无疑会通过同质性带来偏见。

仍然会有大量令人反感的东西被纳入监管的注册表，就像它们影响维基百科这样的系统一样。FOAM 指出了 OpenStreetMap 的问题，它受到恶意破坏和过时信息的影响。虽然标记令牌可能会减少一些低级别的恶作剧，但它不会阻止坚定的用户。防止它们在很大程度上依赖于对代币持有者的积极治理，尽管有激励措施，但我并不认为这是必然的。此外，给这样一个系统赋予价值可能会引发自身的问题。

# **激励错位**

TCR 如何实施激励存在一系列潜在问题。

像 Augur 这样的预测市场需要激励响应者，以便为问题集提供正确的答案。这使得赌注得以解决，并向正确的一方支付。应答者因正确结算赌注而获得奖励(尽管这个过程中有一些模糊的问题)。这可能会导致一些问题。例如，如果一个失败的下注者控制了足够多的被下注的代币，他们可以 51%地攻击系统，这样他们尽管错了也能得到支付。

这是不太可能发生的预兆。撇开写得不好的问题不谈，正确的答案通常是清晰客观的答案。“谁将赢得超级碗”对于大多数应答者来说并不难回答，只需要简单的谷歌。

Ryan Selkis(又名 TwoBitIdiot)认为，AdChain 的 TCR 实现“简单……非黑即白”。

不幸的是，一旦你让公众投票，即使这些看似明确的决定也会迅速转移。精选列表通常依赖于更多的主观品质。在广告链的早期投票中,《脸书时报》和《纽约时报》都遭到了质疑和拒绝。《纽约时报》面临的挑战是由于他们对伊拉克战争的报道[，这是 TCR 不打算考虑或反映的一个因素。](https://cryptoinsider.21mil.com/the-dawn-of-token-curated-registries-an-interview-with-mike-goldin/)

![](img/c626f10c22550631493713aee3271a8f.png)

Photo by [JR Korpa](https://unsplash.com/@korpa?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

这不是一个极端的情况，而是整个游戏。为了防止这种惊人的错误，行动者必须受到激励，以 a)用户和 b)系统的最大利益行事。相反，行动者被激励去为自己的最大利益而行动。

考虑这些例子:

1.  代币持有者会收到代币，用于正确投票。但是正确的投票并不一定导致正确的决定。让我们假设《纽约时报》没有玩弄它的观众指标。将它们排除在 AdChain TCR 之外将是错误的决定。但是，如果我觉得社区会拒绝他们，从经济上来说，我也必须拒绝他们——因为否则我将得不到代币。
2.  我是一家希望上榜的企业。我的竞争对手在名单上，这导致我的公司损失了大量业务。因此，我要么需要进入这个列表，要么——如果被拒绝了——确保这个列表不会被经常使用。因此，我可以向网络发送垃圾邮件，试图确保我的真实提交能够通过。或者我买足够的代币来影响我的投票。或者我发出无数的挑战来封锁网络。这可能会花掉我一大笔钱，但如果这笔钱少于我因不在名单上而持续损失的金额，那么这仍然是值得的。

坏演员或那些在名单上出现的既得利益者会比那些不在名单上的诚实演员更有动力。

这让我想起了我对 Reddit 上试用的 [RecDAO 系统](https://flatoutcrypto.com/home/recdao)的抱怨。它旨在分散对 ethtrader subreddit 的审核，这样用户就可以投票决定帖子应该提升还是删除。这种解决方案的明显问题是，那些关心邮报的人对投票有更大的兴趣。一般人不在乎或者可能不知道。然而，TCR 依赖于获得大量用户，因为否则你还不如只统计 20-30 个做决策的人。这个需要一般人来搞。

达成这种约定不太可能。重大事件的投票率往往很低，更不用说持续治理了。迄今为止，区块链治理的参与度往往很低，这意味着那些参与者产生了巨大的影响。投票需要时间和努力，也需要持续参与。

这种低参与度意味着它通常不是 51%的攻击，而是 5–10%的攻击。当你考虑到仅仅为了挑战一个应用程序，用户通常必须自己出资时，这种情况就更加严重了。这意味着我必须有足够的信心去挑战，也有足够的信心让其他选民投我的票。这是一个不小的坎。

此外，治理通常采取在不定期和分散的基础上对问题进行投票的形式。然而，大多数成功的 TCR 可能需要持续的投票。这意味着选民将不得不每周参与，如果不是每天的话。我不认为这是可能的，因此我更喜欢类似 Messari 的方法，即申请的默认结果是拒绝，而其他人将默认视为批准。这意味着必须达到法定人数才能增加新成员，防止在投票率极低的情况下增加的成员被接受。

不管怎样，让人们投票是一个大问题。为了 TCR 的成功，他们可能需要游戏化或者保持用户的兴趣。我不认为金钱奖励本身就足够了。

![](img/b647d6b34163fbd32e5d512616ca6f96.png)

Photo by [Jeremy Bishop](https://unsplash.com/@jeremybishop?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

# **应用不佳的用例**

虽然目前在数量上有限，但 TCR 目前正被提议用于各种方法。它们中的大部分都不适合 TCR，民用的使用尤其惊人。

新闻是高度主观和情绪化的。使用 TCRs 作为创建“可靠来源”列表的手段是一场地狱里的婚姻。实际上，出版物参差不齐。A 公司的一些记者会很棒，其他的就没那么棒了。《卫报》出版了一份不错的报纸，但是他们的在线点击诱饵记者很糟糕。撇开实际问题不谈，就报纸而言，很难调和左翼和右翼的观点。

我很难看出 TCR 将如何帮助我们。将主观道德判断与支付挂钩似乎不会有好结果。

TCR 将会有其适合度，但可能会比最初设想的更窄。

# **代币型号**

TCR 建立在支持列表的令牌对激励目的有价值的前提下。这导致了一些问题，例如:

*   令牌最初是如何分配的？它们分布得够广吗
*   如果 TCR 成功，这是否意味着需要几千或几万个令牌？
*   如果是这样的话，成百上千的列表如何保持保护它们所需的价值呢？
*   如果代币开始时被低估，而市场赶上了，会发生什么？如果被有限数量的投资者购买，这可能会导致项目的持续风险，并在实现代币价值时带来攻击媒介
*   TCR 将如何解决其他项目面临的问题，如摩擦、法规和交易量不足？

特别值得关注的是初次分配。团队拿走大量的代币对他们没有用处的项目来说已经够糟了——当他们被用来对这些主观问题进行投票时，任何团队都不应该拿走大量的代币。

例如，Adchain 看到一半的令牌供应出售给公众，20%留给 MetaX 和 ConsenSys。这 40%的代币在公开销售后被锁定 12 到 18 个月。我不知道任何一个实体是否在使用他们的代币投票，但同样地，如果他们仍然拥有这些职位，那么他们就可以赢得他们想要的任何选票。信任[中央集权的实体放弃投票](https://block.one/news/block-ones-participation-as-voting-eos-community-member/)通常只持续到人们投‘错’为止。

> 我不一定想要吓走人们(随着群体规范的建立，通过投票击败那些赌注较少的人)。但《纽约时报》实际上输掉了那场[挑战]，作为一个广告令牌持有者，这让我感到不快。所以，现在我个人用我自己的代币更加努力了。但是看着策展过程结束，作为它的见证人，是很有趣的。 [***【迈克戈尔丁】***](https://cryptoinsider.21mil.com/the-dawn-of-token-curated-registries-an-interview-with-mike-goldin/) ***、Adchain 首席工程师(CryptoInsider)***

除此之外，用一个标记来表示一个有值的列表的想法是很不和谐的。就是感觉不‘对’。列表应该有直接形式的值的假设是未经证实的。即使他们最终做到了，考虑到更广泛的加密采用模式，可能需要十年或更长时间基础设施才能得到广泛使用。其他工作令牌似乎更容易实现，可能与 TCR 一样有效。例如，向 ETH 中的用户付费以增加兴趣点是有道理的，广告商或公司能够为地图上更好的位置付费也是有道理的(尽管这听起来很可怕)。花钱买泡沫来维持 TCR 对我来说没有意义。但这正是许多 TCRs 模型的意义所在。

这总感觉像是把目标对准了可笑的项目，所以让我们看看另一个有充分理由的有用的项目，它目前已经处于 TCRs 的最前沿。梅萨里由前面提到的瑞安·塞尔基斯领导，旨在通过引入披露和透明度标准来帮助该行业进行自我监管。这只能是一件好事。

我与这个项目的不同之处在于他们相信 TCR 是成功的工具。这个 TCR 将被用来创建一个符合 TCR 管理者定义的一组标准的项目的白名单。这个想法是:

*   申请人(加密项目)支付 25，000 美元的费用向 Messari TCR (MTCR)申请，提交他们的披露和其他所需的信息
*   管理者(代币持有者)接受或拒绝他们的申请，以及制定透明度标准和认证披露。然而，他们也可以将这项工作委托给验证者
*   验证者由管理者选择并支付报酬(以 MTCR 令牌的形式),以验证和管理白名单
*   消费者使用最终产品，即白名单和相关的内容数据库

Selkis 在[震中播客](https://epicenter.tv/guest/ryan-selkis/)中概述了这种模式将如何工作，其中他提供了大学受托人的例子(TCR 讨论大约在 30 分钟后开始)。受托人或管理人不会审查每一份申请。相反，它们设定了较低层次的验证者必须满足和应用的标准。再说一遍，我认为让一个委员会来制定和批准标准是一个很好的主意。

塞尔基斯还指出，你必须控制最初的发行，并提出了可以邀请 15-20 只基金担任策展人的想法。梅萨里自己也会从供应中分得一杯羹。其他方包括交易所、顾问团和其他合格的投资者。

这引发了一些问题。第一，当各方交织在一起时，拥有分布式团队的优势就丧失了。15 至 20 只基金可能会很快吻合。其次，如果一开始就有一个“相对缺乏流动性”的令牌，你就失去了人们进行验证和监管的一些动力。作为一个题外话，原谅我的冷嘲热讽，但我已经看到足够多的所谓的密码领军人物以这样的方式行事，我不会相信他们作为任何名单的仲裁者的角色。

在这种情况下，TCR 的想法几乎变成了什一税。如果有一群基金在经营 MTCR，那么迫使尽可能多的项目申请 MTCR，从而产生稳定利润的良好来源，将符合它们的最大利益。一年 100 个项目，每次 2.5 万美元，就是 250 万美元，如果有 1000 个项目，就是 2500 万美元。

![](img/0942561cf4a7bfa8a23414ef92122743.png)

Photo by [Derek Story](https://unsplash.com/@derekstory?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

正如塞尔基斯自己指出的那样，梅萨里可以在不使用 TCR 的情况下建造很多他们试图建造的东西。TCR 用于激励数据完整性，并避免困扰 Crunchbase 等公司的数据更新不完整/滞后问题。我不相信 TCR 提供足够的奖励来实现这一点。为什么不能以正常的方式收费呢？据我所知，TCR 是用来激励公司的，而不是个人——那么如果这些信息如此重要，他们会不会为此付费呢？

TCR 所做的是将支付这些信息的责任从尽职调查的基金转移到团队本身。我很乐意接受免费信息，但我不确定这是最好的模式。如果激励被用来获得成千上万的贡献者，我会理解，但由于分析师没有资格获得奖励，他们只去了策展人和验证人(专业公司)，我不确定这种激励模式是否真的增加了很多东西，而不仅仅是创造了一个令牌。

**杂项**

在考虑启动时，除了令牌分发之外，还有其他问题。列表不会有任何内在价值，因为它们对人们没有用处。有一些方法可以解决这个问题，现有的名单可以更好地过渡到 TCR 模式，因此可以进行一种形式的首次代币发行(ITO ),对他们的名单进行数百万美元的估值。

例如，我敢肯定，如果米其林指南决定做一个 ITO，就会有餐馆试图通过购买进入名单。我也相当有信心，这样的举动将对标志性品牌造成不可挽回的损害，鉴于米其林对上市的严格控制，这显然不是他们会考虑的举动。

其次，TCR 的框架至关重要。这可以随着时间的推移而改变，但总的来说，启动时的策展人比后来的贡献者更有能力塑造 TCR 的需求(一旦最初设定，就很难改变)。这本身不是一个问题，但是 TCR 应该注意最初的模糊性可能带来的问题(正如 Augur 所经历的)。

列表的大小也很重要。如果突然有成千上万的项目需要审查，我不确定像梅萨里这样的人会如何应对。我假设他们会以正常的方式扩大规模，但这可能不像其他业务线那样容易，因为其他业务线有明确的合同和业务需求。取而代之的是，在应用程序中有一个简单的上升，然后管理员可以委托给验证者。请记住，验证人员还必须不断检查所有已经被接受的申请人，以确保他们仍然坚持之前的提交。

太小和太大一样是个大问题。如果没有新的应用程序，那么许多 TCR 将会崩溃，因为没有应用程序带来的交易费用。因此，在接纳太多项目和过于排外以至于申请枯竭之间，必须有一条微妙的界限。

最后，还有一些问题，如串通和外链游说，这是很容易想象的。同样，我们对此无能为力(这就是为什么您希望尽可能多地分发令牌),但这是不可避免的。你能做的就是限制它。

**前路漫漫**

与 sto 类似，我认为 ico 面临的审查越少，对它们的批评就越少。ico 本身长期以来被誉为绕过传统金融体系的全球股权融资的革命性形式。现在才发现他们成了大家最喜欢的出气筒。

实际上，我认为当 TCR 在个人层面与更基本的排他性结合在一起，并基于社会资本而非财务资本时，可能会更好。这意味着支付成为保持 TCR 独占的成本，但这是一个非常有限的用例。它也可能对管理列表的爱好者有用。还是那句话，这是社会资本的一种形式，而不是把它们作为创造价值的基础。我认为 TCR 需要某种形式的身份/声誉责任，以配合他们的财务激励。

Twitter 上最近的[TCR party](https://www.coindesk.com/consensys-tcr-party-twitter-token)人气列表，使用 TCR 来形成可信加密人物的列表，应该为 TCR 面临的问题提供了额外的线索。我最初的反应是烦恼，但阅读 Alpine(其背后的 ConsenSys 项目)的评论很有启发性:

> 我的预感是，TCR 将最终成为财阀，富人越来越富，并控制着榜单——史蒂夫·加图索， [CoinDesk](https://www.coindesk.com/consensys-tcr-party-twitter-token)

CoinDesk 指出:

> [格雷戈里]罗科和加图索都对 TCR 持怀疑态度，担心它们不可避免地成为富豪声望竞赛，人们通过象征性持股积聚不成比例的控制权。

人们经常把消极和不喜欢或者一些个人议程混淆起来。这显然是一个比平衡更消极的观点，但是很明显我选择了我认为更有力的例子。然而，我也认为 TCR 面临着大量的挑战，其适用性比通常宣传的更有限。