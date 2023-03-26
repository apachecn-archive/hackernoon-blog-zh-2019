# 通过 python 链接的 sqlmaps 在线赚钱的第 1000 个想法！

> 原文：<https://medium.com/hackernoon/i-1000th-idea-to-make-money-online-via-python-chained-sqlmaps-c8793a6897c2>

![](img/1d5cac476fe20f74f218b82e39dd7827.png)

我的第 1000 个网上赚钱的想法是在一天早上出现的，当时我在玩 Kali 工具，并访问了我不应该访问的东西。当我发现数十个或数千个密码在纯文本中被重复使用，或者创建一个邮件列表来销售不同网站上数十封或数千封电子邮件列表中的商品时，当我想到有机会查看某人的密码是否在其他网站上被重复使用时，就有点道德两难了…但我想我会采取 whitehat 的方法，看看我是否可以让人们意识到他们的一些安全漏洞，以换取向他们销售安全解决方案的机会。

## #1)创建一个用于识别开放数据库或其他安全漏洞的测试自动化脚本

我想到了无数的工具来简化这个过程，但是我发现了一些使用 Scrapy 在 Python 中操纵 sqlmap 和抓取 bing 结果的方法，这允许我启发式地索引暴露的数据库。我会瞄准。在搜索中使用 inurl 参数，在 Bing 结果中带有某些尾随模式的 ca 域名(唉，Google 太难抓取，Bing 容易得多)。

## #2)以非攻击性的方式轻轻穿透他们

如果我愿意的话，我会保存渗透到本地文件中的数据库，以及文件大小大于 0 字节的结果日志，我知道这些日志有数据库名称和入口点，以便查找其他信息。

## #3)收集网站所有者的详细联系信息

接下来，我创建了一个类似 Scrapy 的脚本，它在登录页面上寻找同一个域中其他页面的链接，并从所有相关页面中抓取电子邮件地址和电话号码(通过 RegEx)。

## #4)群发邮件

MailChimp 来救援？我会给他们发送类似“您的数据库名称是 _ _ _ _ _ _ _ _ _ _”的信息，但我们没有进一步深入。“互联网上任何地方的任何人，只要有同样的免费工具，都可以访问你保存的所有信息，比如网站访问者的个人身份信息。”

## #5)打包外包主动 IT 安全解决方案

创建一个登陆页面，出售 IT 专业人士(他们最终会被廉价安置在海外)的专用时间包，现在是时候了。

## #6)重复

然后，在出发时间之后，是重复这个过程的时候了。

是什么让我没有以这种方式利用互联网呢？我给我的律师发了一封电子邮件，说“如果我实施上述计划，我会面临多大的法律诉讼风险”，她回复说“让我们坐下来讨论一下，但首先我们必须确定我们的律师费”，在这一点上，我破产了——正在寻找利用 Bing 呆子的方法——所以我没有继续前进。

喜欢你读过的吗？给我一个关注，并确保观看 Hackernoon 的进展，因为它从 Medium 移动到一个新的改进的平台，用于与此完全一样(并且远远好于此)的故事！