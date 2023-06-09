# 历史上 5 个最愚蠢的数据泄露事件以及你应该从中吸取的教训

> 原文：<https://medium.com/hackernoon/the-5-dumbest-data-breaches-in-history-and-what-you-should-learn-from-them-9122713efa0a>

我们理想主义的幼儿园老师欺骗我们，让我们相信我们是由我们的性格决定的。但是我们现在已经长大了，知道我们的个人身份信息(PII)才是真正定义我们(T2)的东西。没错；不管我们认为自己有多特别，我们仍然只是原子和 PII。

不知何故，在数十亿年的进化过程中，IT 经理和企业主的目的变成了保护他人的 PII。这个命运很无聊。但是，当我们在麻木不仁中放松警惕的时候，我们就会意识到数据泄露、公关灾难和疯狂的求职，希望在被解雇之前辞职。

如果这一切听起来很可怕，确实如此。但是不用担心。许多其他公司已经为你做了愚蠢的工作，所以你可以从他们的错误中吸取教训，避免他们的尴尬。这里有五个光辉的例子，告诉你当你有数据要保护时，不要做什么。

**生命锁**

下次你感到郁闷的时候，只要照照镜子，试试这句口头禅:*“至少我从未做过如此愚蠢的事情，以至于联邦和州政府为整个身份盗窃保护行业制定了法规。”*

当然，这个星球上有一个人*不会*发出那鼓舞人心的圣歌。(我在看你，托德·戴维斯，个人欺诈保护公司 LifeLock 的前首席执行官。)

也许你已经看过托德 2007 年的广告活动，他把自己的社会安全号码贴满了广告牌、电视广告、互联网和卡车侧面。显然，当你向所有人透露你最敏感的信息时，有些人会从中渔利。谁会知道呢？除了所有人？

![](img/78b3aece31994f532a2451e15fc52f33.png)

图片来源: [boingboing](https://boingboing.net/2015/12/15/lifelock-anti-identity-theft-s.html)

没有人对托德·戴维斯在 2007 年至 2008 年间 13 次成为身份盗窃“受害者”感到非常惊讶。他过于自信的广告被监管者认为是“欺骗性的”也就不足为奇了，监管者已经制定了法律来防止将来出现这种说法。

但是 LifeLock 做的最糟糕的事情是给他们的客户提供了一个过于真实的讽刺定义。是的，声称保护 PPI 的公司实际上*暴露了*他们客户的电子邮件信息。

**发生了什么？**

每当客户选择退订 LifeLock 的营销列表，该客户就会被发送到一个典型的*退订*页面。与大多数其他退订页面一样，它显示了客户的电子邮件地址以及以下说明:

*“使用以下字段取消订阅****【john-doe@xyz.com】****【life lock 电子邮件通讯。”*

但是 LifeLock 的退订页面有一个小小的错误。它在取消订阅页面 https-address 中泄露了客户的“订户密钥”。

通过手动更改 https 地址中的订户密钥，任何人都可以调出不同客户的退订页面，每个页面显示不同客户的电子邮件地址。此外，订户密钥是在不使用 GUIDs(全球唯一标识符)的情况下按顺序设置的。)这意味着编写一段代码，对键进行排序，并从每个退订页面中提取每个客户的电子邮件地址，会很容易。哎呦-雏菊。

![](img/86b694bd4e523ff92572f1ab97e33eb8.png)

图片来源: [KrebsonSecurity](https://krebsonsecurity.com/2018/07/lifelock-bug-exposed-millions-of-customer-email-addresses/)

LifeLock 为每个客户设置了世界上最简单的电子邮件钓鱼方案。对于黑客来说，发送虚假电子邮件指导客户通过一个看起来像 LifeLock 支付屏幕的虚假网站进行支付是很容易的。

幸运的是，对于每个 LifeLock 的客户来说，外部安全专家发现了这个漏洞，戴上了他们的好心人帽子，向 LifeLock 昏昏欲睡的耳朵敲响了警钟。暂时避免了危机。(但如果你是 LifeLock 的客户，如果我是你，我会留意他们的退订页面。)

**生命锁的经验教训:**

除了最重要的规则“不要做傻事”，不要太相信别人也很重要。LifeLock 的退订页面由外部合作伙伴管理。当购买处理客户身份的供应商时，做好你的功课。像对待那个想带你女儿去舞会的可疑运动员一样怀疑地对待他们。(他说你可以信任他。但是他们都说。)

如果你从来不喜欢做作业，这里有一个备忘单: [Janrain](https://www.janrain.com/) 是客户身份和访问管理(CIAM)需求方面值得信赖的合作伙伴。他们就像一个无害的聪明的学生，被捉弄了，但随后得到了漂亮的报复，开着宝马 i8 出现在 10 年同学会上。但是我跑题了。

**Equifax**

Equifax 是一家信用报告机构，旨在让地球上的任何人都能像评判不负责任的傻瓜一样评判你。该机构被曝光为比我们其他人都笨。2017 年 9 月，他们不仅允许超过 1.45 亿美国人的私人信息被盗，他们甚至发推文 [*“周五快乐！”*](https://www.cnbc.com/2017/09/08/equifax-tweets-happy-friday-after-security-breach.html) 事发后的第二天。(在此输入暴徒生活太阳镜。)

![](img/f55e645f3d137c937b2035a81ab1e60e.png)

图片来源:[推特](https://twitter.com/darth/status/906244246117552128?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed&ref_url=https%3A%2F%2Fwww.cnbc.com%2F2017%2F09%2F08%2Fequifax-tweets-happy-friday-after-security-breach.html)

哪些类型的信息被盗？没什么。只是大量的姓名、出生日期、地址、社会安全号码、驾照号码、信用卡信息和其他一些零碎信息。所以…没什么大不了的…

当用户对 Equifax [雇佣了一个音乐专业的人作为他们的安全主管的消息完全疯狂时，这也没什么大不了的。](https://www.marketwatch.com/story/equifax-ceo-hired-a-music-major-as-the-companys-chief-security-officer-2017-09-15)或者当他们的前首席执行官理查德·史密斯向众议院能源和商务委员会承认，整个数据泄露事件仅仅是由一名员工的疏忽造成的*。*

当试图找出什么样的新立法可以防止这种事情再次发生时，众议员格雷格·沃尔登对史密斯说，“我不认为我们可以通过一项法律来解决愚蠢的问题。”

**发生了什么？**

发生了修补不足的情况。

服务器和路由器以及公司 IT 环境中的其他设备需要定期修补。对于外行人来说，“修补”意味着在发现系统漏洞时对其进行修复。

Equifax 的员工没有这样做。是啊。就这么简单。

**从 Equifax 吸取的经验教训:**

为 IT 环境打补丁肯定会耗费大量人力。因此，如果你的 IT 员工和 Equifax 雇佣的员工一样(也就是说，他们在工作中忙于玩堡垒之夜，而没有时间担心如何保护你的业务安全)，让像[云管理套件](https://www.cloudmanagementsuite.com/)这样的公司为你修补一切。

另一个教训是雇佣正确的人。寻找那些有着可靠记录的候选人，不要对那些保护公司安全的人的薪水过于吝啬。有时候，经验和一点白发比一个虚高的公司形象更重要。

# 分散自治组织

大多数人都知道(或者声称知道，这样他们听起来会比他们的同事更聪明)，一个分散的自治组织在区块链上运作。

一个这样的组织被简称为分散自治组织(DAO。)它建立在以太坊区块链上，作为使用以太加密货币的风险投资基金。DAO 允许人们向 DAO 社区提出他们的项目想法，希望得到资助。

分散的自治组织开始变得强大。它积累了 1270 万乙醚，价值约为 1.5 亿美元。

该组织的成员和资金都在增长，至今它仍是最强的风险投资公司之一。开玩笑的。刀惨败。

发生了什么事？

分散的自治组织有一个明显的弱点。哪里有愚蠢的弱点，哪里就有肮脏的黑客。

弱点是什么？

2016 年 6 月，一名黑客能够利用 DAO 中的一个漏洞，在系统再次检查他的余额之前，他可以重复相同的交易很多次。

举例来说，想想自动取款机。当然，自动取款机在每次取款时都会检查用户的余额。当一个用户在机器里插入一张银行卡，然后问，*“我能有 1000 美元吗？”，*但是用户的账户里只有 5 美元，ATM 看了一眼，然后说，*“当然，给你，好心的先生！”*或“*对不起，失败者…资金不足。”*

但由于 DAO 代码中的漏洞，当黑客要求提取大量以太币时，系统无法检查余额。黑客的交易是这样的:

黑客:*嗨，道！请问我可以取 1000 美元吗？*

道:*当然可以。给你。*

黑客:*再来 1000 美元怎么样？*

道:*当然可以。*

黑客:*又一个？*

道:那还用说。

这种愚蠢的行为一直持续到价值 5000 万美元的乙醚从“道”中流出，如下图所示。

![](img/b4e005f0bd3ef35695f0e67cfa64586e.png)

图片来源: [CCN](https://www.ccn.com/ether-price-plumets-ethereum-dao-may-be-hacked)

幸运的是，对于道社区的善良人们来说，大部分的钱都被归还了，他们无疑是气疯了。但在此之前，坏黑客和一群勇敢的白帽黑客之间爆发了一场激烈的数字战争。

**注:**下面几段最好边听戏剧电影配乐边读。[这个很好用。](https://open.spotify.com/track/4u4VElxO7JM4IR4jR4TL1s)你戴上耳塞了吗？好了，我们开始吧。

**黑客抓住了一个漏洞。正当黑客(身份不明)准备拿走“道”100%的资金时，他/她的努力神秘地停止了。黑客攻击的暂停为反制措施提供了时间。**

好人的计划。一小群被称为“罗宾汉集团”的好人设计了一个计划来入侵道，耗尽其剩余的货币，并将资金归还给其合法的所有者。

第一次尝试:史诗般的失败！其中一个好人正要“按下按钮”部署反击。但是(听着，)他的网络在他部署计划之前就中断了。是的，那确实发生了。更糟糕的是，启动这一计划的时间非常短。罗宾汉小组错过了短暂的机会。

**尝试二:成功？**几天后，那个坏家伙/女孩黑客又回来了，又开始了他/她的老把戏。但是罗宾汉小组已经准备好了。首先，他们向 DAO 社区发推文说他们正在[耗尽剩余的货币](https://twitter.com/avsa/status/745313647514226688?lang=en)。然后，他们开始排水。万岁。

除了他们还不能喊“万岁”，因为坏家伙/女孩黑客还在试图再次黑回资金。(哇，他/她就是*永不放弃，*他/她呢？这场权力斗争可能会持续到世界末日。但事实并非如此。原因如下。

**重写历史:硬叉子。最后，好人受够了坏人/女孩的恶作剧，所以他们创造了一个“叉子”——这是以太坊区块链的变化。叉子开创了刀的一个全新分支。它通过将道币(以太)恢复到被黑客攻击前的状态改写了历史，这使得其投资者能够拿钱走人。**

安息吧，道。

这整个黑客事件本来可以避免吗？没错。例如， [Zeppelin 写了 15 行代码](https://blog.zeppelin.solutions/15-lines-of-code-that-could-have-prevented-thedao-hack-782499e00942)就可以完成这个任务。

**道的经验教训:**

有些人有一种误解，认为区块链让一切都变得更安全。这个故事是证明事实并非如此的众多故事之一。此外，这个“黑客”真的不是一个黑客。这只是一个邻居小偷偷钱，因为刀的后门开着…没有人在家…饼干留在桌子上…

在你的公司的安全方面有没有任何开放的大门？

**瑞典运输署**

也许这是一个廉价的镜头，但我不能不提到一个政府机构在一个空前的“哑”名单。所以让我们来谈谈 2015 年瑞典运输机构[泄露一切的那段时间。](https://www.nytimes.com/2017/07/25/world/europe/ibm-sweden-data-outsourcing.html)

不，真的。他们泄露了一切可能的事情。

*   秘密特工的名字
*   铁路和海上基础设施的敏感细节，如道路、港口、地铁系统、桥梁等。
*   每位瑞典居民的驾照信息(包括姓名、地址和带照片的身份证)
*   关于瑞典所有车辆的信息，包括民用、警用和军用车辆
*   瑞典证人保护计划中的个人信息
*   瑞典空军飞行员的身份
*   你知道… *那些种类的事情*

根据官方报告，“不知道”广泛的数据泄露是否威胁到瑞典的国家安全。(翻译:*“哦耶。这对瑞典的国家安全没有任何好处。”*)

**发生了什么？**

简而言之，瑞典交通局允许来自外部机构甚至国外的 IT 承包商完全访问上述所有信息。

2015 年，瑞典运输署为了节省资金，将其车辆和牌照注册外包给了 IBM 瑞典公司。IBM 瑞典公司雇佣了欧盟以外的分包商，如罗马尼亚、塞尔维亚和捷克共和国。

除了省钱之外，交通局局长还想节省时间，因此决定忽略一些安全措施。该机构忽视的一个讨厌的安全预防措施是，让敏感信息远离未经安全许可的任何人。

数据泄露后，该机构表示，没有迹象表明这些信息被 IBM 承包商以外的任何人查看过。(我敢打赌，对于证人保护计划中的家庭来说，是一个很大的安慰。)

**从瑞典交通局吸取的经验教训:**

除了不遵守标准协议是绝对不行的这一教训(我们真的还没有学到这一点吗？)，我们也要记住，我们的错误是*我们的*错误。尽管 IBM 雇佣了国际承包商，但 IBM 瑞典公司不应为此受到任何指责。

当一家公司或政府机构变得粗心时，再多的指责也无法满足愤怒的公众。简而言之，做正确的事情*总是*正确的事情，即使它很昂贵或者很耗时。

**一级机器人和控制**

你起了个很好的名字，一级机器人和控制。如果你做了一些不新奇的事情，比如泄露 47，000 份包含福特汽车、丰田汽车、通用汽车、菲亚特克莱斯勒汽车甚至特斯拉的工厂数据记录的秘密文件，那将是一种耻辱。好家伙，*那个*会不会很蠢。哦，等等…你已经*在 2018 年[7 月](https://techcrunch.com/2018/07/20/data-breach-level-one-automakers/?guccounter=1)*做过了？很遗憾听到这个消息。我肯定没人注意到。

好的；既然他们已经离开了房间，让我们畅所欲言吧。Level One Robotics and Controls 是一家总部位于加拿大的公司，提供工程服务。他们专门为汽车供应商进行自动化加工和装配。显然，他们没有足够重视安全的重要性。

**发生了什么？**

近 47，000 个文件通过 [rsync 传输协议](https://en.wikipedia.org/wiki/Rsync)曝光。rsync 服务器不受限制，文件可以下载到任何连接到 rsync 端口的客户机上。更糟糕的是，存放文件的 rsync 服务器是公开可写的。这意味着任何人都可以编辑文档中的数据，甚至将恶意软件加载到文件中。

泄露了什么？合同、发票、工厂布局和蓝图、自动化活动、机器人技术规格和配置、动画、保密协议等等。基本上，肯定有足够的泄露信息让坏人迅速破坏事情。

**从一级机器人和控制中吸取的经验教训:**

首先，不要根据一家公司名字的花哨程度来判断它。(安然和雷曼兄弟也有很酷的名字。记得他们吗？)

第二，了解并时刻掌握组织的安全优势和风险因素。永远不要放松警惕，记住一些基本原则，比如永远保持警惕，知识就是力量，期待意想不到的事情。这些陈词滥调一直存在，因为它们是真实的。

第三，这也是最基本但真实的一点，保持你的数据存储加密。像 [Backblaze](https://www.backblaze.com/) 这样的工具加密数据*和*数据传输。

# 最后的想法

总的来说，从以上五个例子中可以学到的一个普遍的经验是关注基础。你有安全协议。跟着他们！拥抱无聊，不走捷径，投入单调的工作。

最愚蠢的错误往往会导致最灾难性的数据泄露。许多人有着迷人的想法，认为入侵事件的发生通常是因为操着浓重外国口音的老练黑客秘密地从遥远国度的阴影中获得了访问权限。没有。违规通常是因为像本文中讨论的那些愚蠢的错误而发生的。

员工的基本错误也会导致数据泄露，比如一名心不在焉的员工在午休时将一个装有 PII 的 u 盘忘在了麦当劳的浴室里。或者一名员工在周五下午 4:59 将敏感文件扔进垃圾桶，而这些文件本应被粉碎。

底线:保持警惕，提前思考，雇佣最优秀的人。今天的繁重工作意味着明天的宁静。离开恐慌的灾后“我们现在该做什么？”给你的竞争对手开会。至于你和你的公司，你应该更聪明。