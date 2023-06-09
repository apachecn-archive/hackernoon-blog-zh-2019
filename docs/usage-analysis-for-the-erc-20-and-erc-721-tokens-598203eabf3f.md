# ERC-20 和 ERC-721 令牌的使用分析

> 原文：<https://medium.com/hackernoon/usage-analysis-for-the-erc-20-and-erc-721-tokens-598203eabf3f>

*作者 Paul Arssov(披露——我正在*[*ars tech . biz*](https://arstech.biz)*)*

1。 ***简介***

这是一篇技术文章，因此不代表个人观点，而是基于撰写本文时(2019 年 5 月)的实际数据。

ERC20 是一种智能接触标准，是在 ETH 和一些衍生区块链(EOS、Telos……)上执行的程序的基础。ERC721 是该标准的新版本。

文章回答了以下问题-

-区块链联邦理工学院列出了多少 ERC20 和 ERC721 代币？其中有多少是较新的 ERC721 类型的令牌？

-这些 ERC20/721 代币中有多少实际上在中央加密货币交易所上市？

以太坊生态系统充满活力。一个普通人的印象是，即使没有数千个智能合约和硬币，也有数百个——每天都有新的智能合约和硬币冒出来。

![](img/d19628800e536fbb971709deb11ca1e0.png)

2。 ***区块链联邦理工学院上市了多少 ERC20 和 ERC721 代币？其中有多少是较新的 ERC721 类型的令牌？***

以下信息是由一个调用—**blockscout.com**的 REST API 集的程序从区块链以太坊获得的。

该程序的初始版本确实返回了一个包含数百个智能合约的列表和下面的 165 个符号的列表。然后发现程序有 bug！

Here is the initially found list of tokens -
*0 sym-SNX / Synthetix Network Token ERC-20
1 sym-WETH / Wrapped Ether ERC-20
2 sym-REP / Reputation ERC-20
3 sym-OCN / OCoin ERC-20
4 sym-PLANET / 0xUniverse ERC-20
5 sym-XYO / XY Oracle ERC-20
6 sym-SNX / Synthetix Network Token ERC-20
7 sym-WETH / Wrapped Ether ERC-20
8 sym-REP / Reputation ERC-20
9 sym-OCN / OCoin ERC-20
10 sym-PLANET / 0xUniverse ERC-20
11 sym-XYO / XY Oracle ERC-20
12 sym-0x9f8f…. / 0x9f8f…. ERC-20
13 sym-NKC / NeworkCoin ERC-20
14 sym-REN / Republic Token ERC-20
15 sym-MANA / Decentraland MANA ERC-20
16 sym-EDN / Eden Coin ERC-20
17 sym-KBC / KaratBank Coin ERC-20
18 sym-BQTX / BqtX Token ERC-20* ***19 sym-MLBCB / LucidSight-MLB-NFT ERC-721*** *20 sym-ANET / ANET ERC-20* ***21 sym-CK / CryptoKitties ERC-721*** *22 sym-OLT / Oneledger Token ERC-20
23 sym-GEM / Gems Token ERC-20
24 sym-GCC / GameCell ERC-20
25 sym-NEXO / Nexo ERC-20
26 sym-GST2 / Gastoken.io ERC-20* ***27 sym-CTN / Crypton ERC-721*** *28 sym-P3D / PowH3D ERC-20
29 sym-PKG / PKG Token ERC-20
30 sym-nCash / NucleusVision ERC-20
31 sym-Ù¨ / Dentacoin ERC-20
32 sym-OMG / OMGToken ERC-20* ***33 sym-MB / MonsterBit ERC-721*** *34 sym-MTC / Medical Token Currency ERC-20
35 sym-RBLX / Rublix ERC-20
36 sym-TFD / TE-FOOD ERC-20
37 sym-CASH / Cash ERC-20
38 sym-WPR / WePower Token ERC-20* ***39 sym-LAND / Decentraland LAND ERC-721*** *40 sym-EVN / Envion ERC-20
41 sym-JEIG / JeiCoin Gold ERC-20
42 sym-DTA / Data Token ERC-20
43 sym-RGS / Rusgas ERC-20
44 sym-TOL / Tolar Token ERC-20
45 sym-MAN / MATRIX AI Network ERC-20
46 sym-CBF / Chibi Fighters ERC-20
47 sym-SUPR / SupeRare ERC-20
48 sym-BEAT / BEAT ERC-20
49 sym-EMONT / EtheremonToken ERC-20
50 sym-EMPR / empowr ERC-20* ***51 sym-CP / CryptoPony ERC-721*** *52 sym-KEY / SelfKey ERC-20
53 sym-0x86fa0… / 0x86fa0… ERC-20
54 sym-MXM / Maximine Coin ERC-20
55 sym-ATL / ATLANT Token ERC-20* ***56 sym-ETHBOT / Etherbots ERC-721*** *57 sym-C8 / Carboneum ERC-20
58 sym-BCPT / BLOCKMASON CREDIT PROTOCOL TOKEN ERC-20* ***59 sym-FISH / Fishbank ERC-721*** *60 sym-BUNNY / BunnyToken ERC-20
61 sym-BWT / Bittwatt ERC-20
62 sym-ARB / ARBITRAGE ERC-20
63 sym-SCC / SiaCashCoin ERC-20
64 sym-LMM / Link Managenent Chain Token ERC-20
65 sym-BTCG / BitcoinGalaxy ERC-20
66 sym-TREK / TrekChain ERC-20
67 sym-SINOC / Sinoc ERC-20
68 sym-EOP / EOSpace ERC-20
69 sym-CET / Dicet ERC-20
70 sym-ETIT / ETH.TOWN Token ERC-20
71 sym-GAT / GAT Token ERC-20
72 sym-DOG / DOG: The Anti-Scam Reward Token ERC-20
73 sym-DATP / Decentralized Asset Trading Platform ERC-20
74 sym-WAB / WABnetwork ERC-20
75 sym-WNK / Woonk ERC-20
76 sym-EX / EXtereum ERC-20
77 sym-BXT / BITFXT COIN ERC-20
78 sym-ETC7 / Ethereum Legend Coin ERC-20
79 sym-HYDRO / Hydro ERC-20
80 sym-LPK / Kripton ERC-20
81 sym-CMT / Crypto Miner Token ERC-20
82 sym-ZTH / Zethr ERC-20
83 sym-BDT / BitDATA Token ERC-20
84 sym-PDATA / PDATA ERC-20
85 sym-O2O / O2O ERC-20
86 sym-OPEX / Optherium ERC-20
87 sym-XBD / Bit Dinero ERC-20
88 sym-EON / EOS Network ERC-20
89 sym-QZT / QZ Token ERC-20
90 sym-PRCLS / PRICELESS ERC-20
91 sym-BCT / BCT Token ERC-20
92 sym-PYT / Payther Token ERC-20
93 sym-BMAX / BitcoinMax ERC-20
94 sym-DW1STR / Dark Winds First Edition Cards (Revisited) ERC-20
95 sym-CPR / Casper ERC-20
96 sym-TBE / TowerBee ERC-20
97 sym-YEED / YGGDRASH ERC-20
98 sym-TUP / turepay ERC-20
99 sym-ZTHG / ZethrGame ERC-20
100 sym-GEX / GREENX ERC-20
101 sym-NN / Neodium Network ERC-20
102 sym-MORPH / MORPH ERC-20
103 sym-GVINE / GVINE ERC-20
104 sym-IOG / IOGENESIS ERC-20
105 sym-POC / ProofOfCommunity ERC-20
106 sym-RST / REGA Risk Sharing Token ERC-20
107 sym-CCN / CryptoCurrencyNetwork ERC-20
108 sym-XMT / Marijuana ERC-20
109 sym-BABC / Business Alliance Business Coin ERC-20
110 sym-ONTOP / On Top Coin ERC-20
111 sym-NOE / NoteOfExchange ERC-20
112 sym-EML / e-Mal Token ERC-20
113 sym-OGO / OGO Coin ERC-20
114 sym-ETA / ETA ERC-20
115 sym-ZUR-D / Zur Drafts by Zurcoin Core ERC-20
116 sym-0x2c2391f… / 0x2c2391… ERC-20
117 sym-DMX / Dreamex Token ERC-20
118 sym-JEANS / Jeans Token ERC-20
119 sym-CLM / Caelum Token ERC-20
120 sym-MGC / Magic ERC-20
121 sym-ProductionUnit / Production Unit | Moon, Inc. ERC-20
122 sym-UBN / Ubricoin ERC-20
123 sym-PWM / POWM ERC-20
124 sym-CM / CM ERC-20
125 sym-POCG / CraigsABitch ERC-20
126 sym-BIT / 8thereum ERC-20
127 sym-DDT / DailyDivs ERC-20
128 sym-STEEM / Steem ERC-20
129 sym-RMB / LIYAN ERC-20
130 sym-SB / èµå¸ ERC-20
131 sym-0xbb991… / 0xbb991… ERC-20
132 sym-ETD / Ethereum Diamond ERC-20
133 sym-TKBC / Token Bit Coin ERC-20
134 sym-UFT / Unoflix ERC-20
135 sym-SST / SocialStake ERC-20
136 sym-J20 / JIL Coin ERC-20
137 sym-GBT / GitBit Token ERC-20
138 sym-AL / ALpay ERC-20
139 sym-LUKE / LUKE ERC-20
140 sym-0xa6ff73… / 0xa6ff73743… ERC-20
141 sym-SCALE / SCALE ERC-20
142 sym-Snow / Snow ERC-20
143 sym-WE.R.LIVE / Polymath Test Token ERC-20* ***144 sym-WTOA / WeTrust Token of Appreciation ERC-721*** *145 sym-FUNDS / FUNDS ERC-20
146 sym-YMOM / Your MOM ERC-20
147 sym-SYTZ / ä¸‰å…ƒé€šè¯ ERC-20
148 sym-BATCoin / BATCoin Token ERC-20
149 sym-EIX / DeniX ERC-20
150 sym-GLASS / sharespost ERC-20
151 sym-LINKURL / UrlLinkCoin ERC-20
152 sym-XRH / xurihong ERC-20
153 sym-TT / Tiger Token ERC-20
154 sym-BC12 / Bavli Coin ERC-20
155 sym-IDOL / IDOLCOIN ERC-20
156 sym-DRGN / Dragon ERC-20
157 sym-BAX / BAX ERC-20
158 sym-0xBTC / 0xBitcoin Token ERC-20
159 sym-ESS / ESSENTIA ERC-20
160 sym-ABC / ABC — Anti Bureaucracy Coin ERC-20
161 sym-EVO / Evolution ERC-20
162 sym-FSBT / Forty Seven Bank Token ERC-20
163 sym-MNZ / Monetize Coin ERC-20
164 sym-UBEX / UBEX Token ERC-20
165 sym-HOT / HoloToken ERC-20*

在再次运行该程序后，修复了错误，我得到了一个包含 110，000 多个智能合同的列表。该程序运行了几天，才实际获得代表这些 110 万智能合约的令牌数。

一些令牌/智能合约不包含符号和名称，并被列为— 0x…..也许它们代表了旧令牌或即将到来的新令牌的开发阶段。

在 110 万个智能联系人中，该程序确实找到了大约 7150 个令牌。列表中的一些代币名称与流行的加密硬币相匹配——BTC、LTC、BCH、DOGE……代表 ex。我为 XRP 找到了这些代币-

…3050 XRPC —瑞普卡什/ ERC-20
…3420 XRPE —瑞普 EOS / ERC-20
…3897 XRPB —瑞普黑/ ERC-20
..5735 IXRP —伊里普/ ERC-20
…7102 XRP —里普/ ERC-20

这是相当具有欺骗性的！一个用户购买了以太坊区块链上的这些代币中的一个，可能会认为它在某种程度上与 Ripple 和它的链有关，但很可能根本没有关系。

同样令我惊讶的是，新的 ERC721 令牌数量很少。似乎只有 ETH 生态系统中最成功的令牌，如 CK (Crypto Kitties)和少数其他令牌是基于 ERC721 标准的。

3。 ***有多少区块链联邦理工学院的 ERC20/721 代币实际上在中央加密货币交易所上市？***

回答这个问题的信息是通过一个程序在 [**arstech.biz**](https:/arstech.biz) 从我们的自动加密货币交易系统中浏览数据获得的。

该系统从分布在世界各地的 36 个以上的主要中央加密交换中心不间断地收集信息。

集中式加密交换是一种或多或少受管制的业务，其运营必须遵守注册国的法律。这种兑换通常能够将加密硬币兑换成法定货币(美元、欧元、日元、韩元……)。

相比之下，区块链联邦理工学院几乎没有具备去中心化加密交换能力的智能合约。它们允许在同一个区块链以太网上的任何 ERC20/721 令牌之间进行交换。

以下是实际上在集中式加密交换中列出的 ERCxxx 令牌列表，取自上面的 165 个令牌列表，后面是交换和符号-

*0 SNX —库币- SNX-ETH，* ***1 REP—hit BTC- REPETH，bitfinex- REPETH，bithumb- REP，币安-REPETH，coinone- rep，simex- REP_ETH，
2 OCN — hitbtc- OCNETH，bithumb- OCN，库币- OCN-ETH，huobi- ocneth，lbkex- ocn_eth，*** *3 XYO —库币- XYO* ***7 MANA—hit BTC- MANAETH，kucoin- MANA-ETH，币安-MANAETH，bibox- MANA，huobi- manaeth，okex- mana_eth，*** *8 EDN—kucoin-EDN-ETH，
9 KBC — hitbtc- KBCETH，digifinex- eth_kbc，bitforex- eth-kbc，
10 OLT — kucoin- OLT-ETH，bite okex- omg_eth，
13 MTC — kucoin- MTC-ETH，bibox- MTC，lbkex- mtc_eth，dobitrade- mtc_eth，* *14 RBLX—quoine-RBLXETH，
15 TFD — kucoin- TFD-ETH，
16 WPR — bitfinex- WPRETH，币安- WPRETH，huobi- wpreth，

22 MXM — coinbene- MXMETH，bitforex- eth-mxm，
23 BCPT — hitbtc- BCPTETH，币安- BCPTETH，idcm- BCPT/ETH，
24 FISH — bcex- IFISH，
25 GAT — quoine- GATETH，bcex- GAT，
26 WAB —币安- WABIETH，
27 HYDRO — bitforex- eth-hydro，* T55
30 MORPH—hit BTC—MORPHETH，
31 MGC—idcm—MGC/ETH，
32 BIT—hit BTC—BITETH，
33 STEEM—bith um—STEEM，币安—stee meth，霍比—stee meth，
34 GBT—BIT forex—ETH—gbt，
35 DRGN —库币—DRGN—ETH，
36 BAX —库币—BAX—BAX

如列表所示，大部分列出的 ERCxxx 令牌都在一个交易所上市。

一小部分令牌在 3 个以上的加密交易所上市，如突出显示的那样。然而，需要进一步的分析来发现差价和交易量。

高价差——买卖价格之间的差异阻碍了加密硬币的首次购买和交易。低(或没有)24 小时交易量表明对特定加密硬币交易的低受欢迎程度和兴趣。

尽管如此，名单上的所有硬币都显示了打破以太坊区块链泡沫的勇气，并在公开的秘密市场上进行交易。

4。 ***结论***

正如我在开始时指出的，这篇文章包含的观点较少，事实较多。这两个列表可以用作特定加密硬币的交易和/或发行特定加密硬币的企业的投资的参考。

商业教授克莱顿·克里斯滕森(Clayton Christensen)将加密货币定义为一种“颠覆性创新”。

我们正在见证一个新市场的诞生，它正在扰乱金融市场，并有可能“吃掉”传统股票市场的“午餐”。

*未来文章主题-
-中央加密货币交易所上市的 ERC20/721 代币的价格、价差和交易量是多少？
-分析以太坊区块链上成功的 ERC20/721 代币的源代码和功能*