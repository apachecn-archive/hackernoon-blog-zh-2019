# 数据泄露:它们如何影响人们以及我们如何应对它们

> 原文：<https://medium.com/hackernoon/data-breaches-how-they-affect-people-and-what-can-we-do-to-fight-them-859b902ed330>

![](img/190cfb5015cd9ecbeecd1ba3a3e96e2a.png)

Photo by [ev](https://unsplash.com/photos/gpjvRZyavZc?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/privacy?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

如今，一切都在“云中”运行:应用程序、软件基础设施和数据。不仅是应用程序数据，还有您的个人数据。这些规则是大多数为更好的未来构建工具的团队的首要考虑。

与此同时，每周都会有新的数据泄露新闻。足够可怕的是——一些应用程序存储你的护照/身份证照片、信用卡等——所以，是的，数据泄露是一个值得警惕的理由。虽然有些人可能认为，如果他们没有参与非法活动，他们的隐私就不重要，但这实际上关系到我们所有人，而且问题要复杂得多。

![](img/12cb4a688b8da878a1b3805915cb2b5f.png)

我们是唯一关心自己隐私的人，应该向服务提供商要求这种保护。在企业内部，数据泄露对消费者来说可能是灾难性的，但对企业来说却不是。例如， [Equifax 数据泄露:](https://www.gao.gov/products/GAO-18-559)

*“2017 年 9 月 7 日，Equifax 透露，对其信用报告数据库长达数月的非法访问导致超过 1.43 亿人的个人身份信息被泄露，几乎所有人都在美国* ***截至 2018 年 3 月，受影响的总人数超过 1.48 亿。该公司等了六个星期才披露违规行为。* ***各种记录包括信用卡、驾照、社会安全号码、出生日期、电话号码和电子邮件地址。*****

*你可能会认为，如此肮脏的事件暴露了如此大量的记录，并使那些受影响的人完全容易受到身份和信用滥用的影响，至少会推动新的法律和方法来不惜一切代价保护数据。至少可以说，这个结果并不令人满意。在一些地方，法律正在更新以保护公民，但这些努力还不够。罪犯和企业不关心惩罚，或者[马克·扎克伯格是否会因为滥用、刺探和出售全球数百万人的数据而再次被送上法庭](https://www.nytimes.com/2018/04/10/us/politics/mark-zuckerberg-testimony.html)。*

*但这些都不是孤立的事件。仅在 2018 年，人们就成为了**1293 起数据泄露事件的受害者，泄露了超过 1.74 亿条记录，这些事件发生在联邦快递、运动品牌阿迪达斯和安德玛、萨克斯第五大道、加密交易所如 Bithumb、Ticketmaster、加拿大航空、T-Mobile、** [**等公司，还有很多……**](https://www.identityforce.com/blog/2018-data-breaches)*

*面对这些证据，我们不能忽视这样一个事实，即我们需要工具来保护现有的软件，并以消费者为中心开发新的软件，以对抗数十年的滥用。我们需要由技术专家打造的工具，他们了解网络攻击背后的细节，**他们了解拥有安全硬件的价值，他们重视用户的数据并致力于此。***

*这是有解决办法的。基于 Enclave 的计算就是其中之一。enclave 保护数据，确保其完整性和机密性。当在 enclave 中计算数据时，主机是否受到威胁并不重要。英特尔的 SGX 是迄今为止最先进的 enclave 技术，为这一问题提供了完整的解决方案。然而，飞地远非完美——它们很难使用。我们需要对最终用户“透明”的工具，这种工具不需要试图采用它们的开发人员付出巨大的开销。这就是为什么假人作为石墨烯工作组的一员，参与构建一个支持无缝使用 SGX 的框架，这个框架能够以最低的成本在任何地方实现基于飞地的计算。*

*如果我们实现了这些目标，我们就可以释放基于 enclave 的计算的潜力，并准确构建人们防止这些违规行为所需的内容。**然后，您的角色将是向服务提供商请求这种保护。***

*然而，[构建石墨烯绝非易事。](https://blog.golemproject.net/golems-essential-guide-to-graphene/)它需要参与[项目](https://grapheneproject.io/)的许多人的协调，因此它是同类中的第一个——以前从未建造过——它需要大量的技术知识和顶级质量工程师的参与。如果你是其中之一，请加入我们的项目！。从好的方面来看，它可以改善数百万人的生活。*

*假人有什么好处(除了名誉和荣耀；)?*

*如前所述，确保数据完整性和保密性是我们的首要任务。没有这些，我们无法建立一个可靠的假人网络。当假人扩展时，全世界数以百万计的 CPU 和 GPU 将通过 p2p 连接起来，并为彼此运行计算。我们需要确保这样的计算不会被主机(计算任务的人)影响或篡改。*

*例如，如果你是一名神经外科医生，你需要做核磁共振才能看到病人的疾病。为此，你需要强大的计算能力。在自己的笔记本电脑上做需要更长时间，使用云提供商也不总是安全的。使用石墨烯来验证结果并确保数据安全将有很大帮助。您需要确保大脑扫描是准确的，并且渲染的图像没有被利用。无论您是神经外科医生、处理数百万 id 的公司，还是电影动画艺术家，隐私和不受损害的数据都是您最重要权利的一部分。*

*对于假人来说，一个核心目标是建立工具，确保你的数据和后续工作不会受到损害，而 SGX/石墨烯是这些努力的关键组成部分。*

*在网络世界中，数据安全性和完整性的关键是尽可能减少表面攻击。我们的答案是 SGX/石墨烯耦合。攻击者总是会尝试他们的手段，但是如果全世界的开发人员都掌握最新的技术，构建和采用石墨烯的集体努力可以对攻击缓解产生极其积极的影响。*

****我们致力于构建石墨烯，并通过其无缝可用性创造一个采用漏斗。*** *终端用户需要意识到他们所面临的危险，以便提高意识并接触到开发者，他们的应用可以从石墨烯等隐私保护工具中受益。**