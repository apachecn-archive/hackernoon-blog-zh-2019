# 离开苹果和谷歌:/e/实际上是如何脱离谷歌的？

> 原文：<https://medium.com/hackernoon/leaving-apple-google-how-is-e-actually-google-free-1ba24e29efb9>

![](img/5bf1d236d55b768a61fb9d7a018671a8.png)

昨天，我们已经开发了一年的以隐私为重点的 [/e/移动生态系统](https://e.foundation)，已经在[的《信息安全手册》中进行了介绍，](https://infosec-handbook.eu/blog/e-foundation-first-look/#e-foundation)重点关注隐私问题和系统的实际“去谷歌化”。

作者提出了一些担忧，并总结道“虽然/e/看起来很有前途，但它现在还不是谷歌免费的。”

# 太好了！

我很高兴一些安全和隐私专家开始密切关注/e/，并对我们正在做的事情提出挑战:了解专家如何考虑该项目对我们来说极其有用。这也非常有帮助，因为它提高了期望值，因此鼓励我们做得更好，改进产品。

然而，我认为，即使/e/仍然是测试版软件，因此还不完善，但回答本文中提出的一些问题，并详细说明我们的状态、目标和路线图是很重要的。

# 已回答的索赔和问题

我们走吧:

***其会员必须缴纳年费***

虽然我不确定作者在这里指的是什么，但对我来说重要的是要提醒:

*   /e/是一个开源项目，为了公众利益，由一个非盈利组织提供支持
*   作为一个开源项目，所有用于/e/操作系统(从 AOSP/linegeos 派生而来)和/e/的核心在线服务的源代码都[公开](https://gitlab.e.foundation)
*   任何人都可以下载/e/ builds(目前可以在大约 60 种不同的智能手机上下载)和/e/的源代码，并且可以自由安装或编译 ROM

***“总之，安装/e/就像安装 LineageOS 一样简单。您不需要他们要求中所述的/e/帐户。”***

我们的网站上没有使用/e/ account 安装 ROM [的要求:](https://gitlab.e.foundation/e/wiki/en/wikis/devices-list)

> *"可选:如果您希望从/e/ account 集成中受益，以获得所有在线服务，如:电子邮件、驱动器、日历、笔记、任务，建议您拥有一个/e/ account(如:*[*John . doe @ e . email*](mailto:john.doe@e.email)*)。为了得到一个测试/e/帐户，请在这里阅读说明*[](/e/wiki/en/wikis/create-e-test-account)**。”**

****“然而，有些人无论是否使用手机，都可能不喜欢手机上预装的信号和电报。”****

*绝对的。这就是为什么:*

1.  *我们将很快添加一个新功能，让用户从/e/中卸载大多数默认(预装)应用程序*
2.  *明年夏天，我们将在安装期间引入不同的用户配置文件，这将影响默认应用程序的选择*

****“重启手机后我们监控了/e/的所有数据连接。首先，/e/通过使用它的连通性检查来敲 Google 的门:“****

*正如本文接下来所述，我们的 Gitlab ( [#146](https://gitlab.e.foundation/e/management/issues/146) )报告了这个问题以及 DNS 问题。*

*当然，这是我们希望在发布/e/ v1.0 之前解决的问题。*

****“其他用户反映/e/默认使用谷歌的 DNS 服务器(如 8.8.8.8)。”****

*这不是真的:我们已经对源代码做了全面的审查，特别是仿生，Android 的自定义 libc。*

*结论是 8.8.8.8 和 2000::只是[用于仿生](https://github.com/aosp-mirror/platform_bionic/blob/master/libc/dns/net/getaddrinfo.c#L388)来[弄清楚](https://github.com/aosp-mirror/platform_bionic/blob/master/libc/dns/net/getaddrinfo.c#L1935)是否有一些 IPv4 或 IPv6 可用。*

*否则，DNS 服务器由网络提供商使用 DHCP 来设置，并且只能使用 WiFi 访问来强制执行。*

*因此，我们开发并在最近推出了一项功能，让用户可以根据自己的意愿强制执行 DNS 设置:*

*![](img/4f26717dc85f4edc858e6a55f93a280b.png)*

****“设置允许您设置默认 DNS 解析器(设置→无线&网络→更多→ DNS →禁用“使用网络 DNS”→设置要使用的 DNS)。我们尝试过，但路由器会强制执行网络的 DNS 解析器。”****

*尽管它在工作，除非我们在某处有一个错误，或者除非路由器正在重写 DNS 请求。我们将再次检查，以确保这项新功能按预期工作。*

****“此外，还有通过 IPv4/IPv6 来自/去往***[***www.google.com、***](http://www.google.com,)***gstaticadssl.l.google.com、googleadapis.l.google.com 和 www3.l.google.com 的 TLS 1.2 加密流量。”****

*感谢您的报告，我们会看看，它需要修复。*

****“NTP 同步导致许多不同的域名得知你的 IP 地址”****

*从用户数据隐私保护的角度来看，这可能不是一件非常具有挑战性的事情，至少谷歌不会这么做。*

*事实上，也许我们应该整理出 NTP 服务器的列表，只保留“可信的”，如果存在的话。和/或添加一些/e/ NTP 服务器。*

****“总而言之，天气 app 泄露了你的 IP 地址，你的设备的身份，也许还有你的位置(城市名，GPS 坐标)。所有内容都以明文形式发送。”****

*天气应用程序将得到改善，使用 HTTPS 和删除用户代理。然而，很明显，它将继续向 OpenWeatherMaps 发送 GPS 坐标(顺便说一下，这不是 Google)。否则，不可能有基于当前位置的天气服务。*

*请注意，可以在设置中禁用发送地理位置:*

*![](img/491320e0d5b35da7fd5f189ee7f679a4.png)*

****“所以，目前还不清楚通用魔法公司以明文形式发送/接收了什么样的信息。”****

*MagicEarth 为我们提供了一份关于隐私的[相当全面的文档](https://gitlab.e.foundation/e/wiki/en/uploads/8befe8953601260ec5b633ddc80a9c58/User_Data_-_Privacy_20180906_v06-1.pdf)，我们正在与他们合作改进这方面的内容。我们将与他们讨论未加密流量的问题。*

# *关于 e 基金会网站*

*我们意识到我们在网站上使用的一些内容管理系统存在一些问题，特别是 Wordpress。*

*这里需要理解的重要一点是,/e/项目的承诺是提供一个移动生态系统，ROM +基本的在线服务，更加尊重用户的数据隐私。第一步是尽可能地“取消谷歌搜索”。*

*因此，我们专注于产品:*

*   */e/ ROM*
*   */e/在线服务:驱动器、日历、笔记、任务、电子邮件、元搜索引擎(很快会有 Android 应用程序库)*

*我们的主要问题是我们为 e.foundation 使用的 CMS(Wordpress ),因为[不确定他们是否真的关心数据隐私](https://core.trac.wordpress.org/ticket/46169)。因此，即使这方面超出了承诺的项目范围，如果这没有改善，我们可能会转移到另一个 CMS。*

****“我们已经在一月份就谷歌字体的使用联系了/e/ Foundation，但是，我们至今没有得到答复。”****

*这和上一点联系在一起，[公开讨论过](https://community.e.foundation/t/e-foundation-says-degoogle-your-life/2594)。*

*还请注意[我们在网上有隐私政策](https://e.foundation/privacy-policy/)，虽然可能并不完美，但它旨在告知用户我们在网站上使用了什么。*

***结论***

*我们认为，如果/e/在保护用户数据隐私方面还不完善，我们正在努力。当然我们会继续努力，让它变得越来越好。可能/e/已经是在“解除封锁”和保护用户数据隐私方面最先进通用移动生态系统:*

*   *不使用谷歌搜索*
*   *没有使用谷歌应用程序*
*   */e/即将向 Google 发送 0 个数据*
*   */e/提供对所有基本联机服务(驱动器、邮件…)的替换*

*我们将在我们的网站上列出所有剩余的问题，以便用户了解当前的状态。*

*然而，我想再次感谢 InfoSec Handbook 和这篇文章的作者对/e/的全面评论和非常有价值的反馈。*

*你真诚的，*

*gal Duval/e/创始人。*

*在推特上关注我/【乳齿象上的 *

*PS 读者可能有兴趣了解更多关于/e/ 的[:](https://e.founndation)*

*三篇创始文章:*

*   *[离开苹果和谷歌:我的“eelo odyssey”——简介](https://hackernoon.com/leaving-apple-and-google-my-eelo-odyssey-introduction-d22741f990d7)*
*   *[离开苹果和谷歌:我的“eelo odyssey”——第一部分:移动操作系统](https://hackernoon.com/leaving-apple-and-google-my-eelo-odyssey-part1-the-mobile-os-f378ee247315)*
*   *离开苹果和谷歌:我的“eelo odyssey”第 2 部分:Web 服务*

*此外:*

*   *[/e/不仅仅是技术，它是一个自由和民主的社会项目](https://hackernoon.com/eelo-is-more-than-tech-its-a-societal-project-for-freedom-and-democracy-951ea5c8f162)*
*   *[/e/首个测试版公告和说明](https://hackernoon.com/leaving-apple-google-e-first-beta-is-here-89e39f492c6f)*