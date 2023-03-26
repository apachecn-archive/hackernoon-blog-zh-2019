# 要警惕新的比特币骗局

> 原文：<https://medium.com/hackernoon/new-bitcoin-scams-to-look-out-for-8242d78d2a66>

![](img/2b47c6a92c662de0366f5e6700bfd910.png)

过去几年，加密货币市场参与者目睹了比特币价格的快速上涨和大幅下跌。在 2017-2018 年从近 2 万美元暴跌至 6000 美元，甚至在 2019 年初跌破 4000 美元的门槛后，这种受欢迎的加密硬币的价值在今年春天开始反弹，达到 8000 美元。此外，专家[预测再过两年，BTC 将迎来新一轮繁荣。](https://www.ccn.com/bitcoin-price-will-triple-to-20000-by-2021-investment-bank-canaccord)

虽然最近的趋势对饥渴的投资者来说看起来很有希望，但它似乎也成为了网络犯罪分子重新激活他们在比特币生态系统中的恶作剧的主要驱动力。在不太遥远的过去，加密货币爱好者主要是欺诈性 ico(初始硬币发行)、虚假硬币兑换要约和庞氏骗局的目标。现在，这些骗局又多了一种恶意软件的味道。下面的例子揭示了克鲁克斯投资组合中的新花招。

**比特币诈骗推送勒索软件**

2019 年 5 月下旬发现的一波骗局[一直在传播勒索软件，最近，在一个名为比特币收集器的实用程序的伪装下，出现了一种信息窃取感染。粗略的报价被宣传为一种通过简单运行软件赚取 15-30 美元比特币的方式，没有任何附加条件。此外，骗子们承诺 1000 英镑可获得 3 个以太坊(约 735 美元)，通过个人推荐链接进入他们的网站。](https://twitter.com/x42x5a/status/1130421342782857217)

几乎不需要任何努力就能立即制造加密硬币的能力是一个很容易让人上钩的陷阱。一旦用户点击继续，他们就会被转到比特币收集器应用程序下载链接。为了给这一策略增加一些表面上的合法性，该页面提供了一个 VirusTotal 链接，据称可以证明该文件的检测率为零。然而，这种虚拟检查只是做做样子，与产生的恶意负载没有任何关系。

这个可疑的下载文件是一个 ZIP 文件，当它被解压缩时，包含了一大堆项目。其中一个是名为 BotCollector.exe 的二进制程序，它执行流氓比特币生成器。然而，事实上，陷阱“free bitco . in-Bot”程序启动了最后阶段的恶意软件有效载荷。在大多数情况下，它是一个名为 Marozka Tear 勒索软件的勒索软件样本。这种害虫找到并加密受害者的大部分个人文件，用。加密扩展。它扔下一张勒索信，提供了通过支付恢复数据的进一步说明。这当然是一个不利的情况，但对感染者来说也有一些好消息。罪魁祸首原来是臭名昭著的开源隐藏撕裂勒索软件的衍生产品，这意味着它可以免费被[解密](https://www.bleepingcomputer.com/ransomware/decryptor/how-to-decrypt-hiddentear-ransomware-variants/)。

然而，在某些情况下，通过比特币收集器骗局发射的有效载荷可能是信息窃取者。目前正在旋转的是巴德尔。当攻击正在进行时，感染会到达犯罪分子的 C2 服务器，并等待有关在受感染的主机上收集数据类型的命令。巴德尔能够收集和过滤网站和浏览历史的认证细节。最重要的是，它可以截图和窃取任意文件。鉴于此特洛伊木马的众多可疑特征，感染上述勒索软件似乎是两害相权取其轻。

**可疑的 YouTube 视频支持恶意软件充斥的比特币骗局**

那些寻求快速轻松获得加密货币的人是在 YouTube 上流传的另一个比特币骗局的目标受众[。恶意行为者一直在宣传比特币生成器软件，据称该软件允许用户毫不费力地赚取硬币。与上述方案相反，这场运动依赖于 YouTube 视频，这些视频将这笔交易描述为自切片面包以来最好的事情，并提供下载该工具的链接。](https://www.newsbtc.com/2019/05/29/crypto-scam-alert-youtube-videos-promoting-bitcoin-generator-really-pushing-malware/)

然而，这些声称只不过是一个烟幕，欺骗人们下载一个代号为 [Qulab](https://fumik0.com/2019/03/25/lets-play-with-qulab-an-exotic-malware-developed-in-autoit/) 的木马。有害有效载荷托管在 pCloud 加密存储平台上。启动后，它会对主机执行彻底的侦察。特别是，Qulab 特洛伊木马窃取网站和游戏相关服务(如 Steam 和 Discord)的登录凭据。它还搜索 FileZilla FTP 应用程序以获取保存的认证数据，窃取浏览器 cookies 和加密货币钱包信息。

Qulab 最令人不安的特性之一是它篡改了 Windows 剪贴板。该恶意软件跟踪受害者复制到剪贴板的信息，重点关注符合典型加密货币地址模式的项目。当发现匹配时，木马会偷偷用另一个地址替换它，这样每当用户发送比特币时，资金就会流向犯罪者，而不是正确的接收者。

**关闭大型混合网站让骗子的日子更难过**

2019 年 5 月，荷兰财政信息和调查局查封了全球最大的比特币混合服务之一 BestMixer.io。这是一次[精心协调的行动](https://www.europol.europa.eu/newsroom/news/multi-million-euro-cryptocurrency-laundering-service-bestmixerio-taken-down)，另外还涉及欧洲刑警组织和卢森堡当局。这源于荷兰执法部门与 McAfee 安全公司合作进行的长达一年的调查。

犯罪分子经常利用 Mixer 网站或 tumblers 来清洗非法所得。他们争夺加密货币的流动，收取费用，向当局隐瞒其真实来源。据报道，BestMixer.io 于 2018 年 5 月推出，一年内营业额达到 2 亿美元。根据调查人员的调查结果，这一数额中有相当一部分来自犯罪来源。

反洗钱举措导致查封了与该混合器相关的 6 台服务器，从而阻止了其欺诈活动。显然，犯罪分子现在不得不寻找替代方法来掩盖他们的非法比特币交易。

**比特币骗局保护技巧**

在决定交易策略和参与任何诱人的区块链风险投资之前，强烈建议公司和普通用户仔细检查其声誉，寻找知名市场影响者的意见，并阅读细则以识别潜在的危险信号。各种承诺即时收入的比特币“生成器”和“收集器”最有可能掩盖危险的勒索软件或间谍软件负载。企业应该避免投资据称能保证快速投资回报和利润的比特币项目——这些说法通常伴随着 ICO 退出骗局和金字塔计划。总而言之，如果加密货币看起来好得不像真的，经验法则是远离它。