# 目前使用的主要安全架构是什么？

> 原文：<https://medium.com/hackernoon/what-are-the-primary-security-architectures-in-use-today-ded1080e7e5e>

![](img/1c300e0347c7a891b31d9c3ccde1e966.png)

Photo by [Rubén Bagüés](https://unsplash.com/photos/_DkmMhzrsYY?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/security?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

在我最近的一篇关于“[零信任架构的兴起](https://hackernoon.com/the-rise-of-zero-trust-architecture-17464e6cbf30)”的文章中，我写到了这一相对较新的概念在网络安全领域的广泛和快速采用。然而，目前仍有其他几种安全架构在使用:

# 传统网络边界安全

传统的网络边界安全由许多不同的部分组成，所有这些部分共同为网络提供安全解决方案。

传统上，网络安全从用户认证开始，通常使用用户名和密码。这种方法也称为单因素身份验证，双因素身份验证需要验证另一个项目，例如手机、USB 驱动器，甚至某种令牌。在更高级的一端，还有三因素认证，这将涉及用户的生物特征，如视网膜或指纹扫描。

一旦用户通过验证，防火墙将通过限制用户在网络中可以访问的内容来确保访问协议得到遵守。这是防止他人未经授权访问网络的非常有效的方法。此外，网络上两台主机之间的通信可以加密，为网络提供额外的安全保护。

![](img/b3a83cb2a3ca9a63ec17c2376e38ca62.png)

Photo by [Thomas Jensen](https://unsplash.com/photos/ISG-rUel0Uw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/network?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

一些企业也可能部署蜜罐。蜜罐本质上是一种网络资源，在网络中充当诱饵。因为蜜罐不用于任何合法的商业目的，所以它们既可以用作监视工具，也可以用作一种预警系统。这意味着如果一个蜜罐被访问，通常是有问题的。安全团队可以分析对蜜罐的攻击，以跟上新的攻击。然后，通过突出显示以前未知的漏洞，可以将这些发现应用于进一步提高真实网络的安全级别。

类似于蜜罐，蜜网是一种诱饵网络，它是通过故意的安全缺陷建立起来的。这些旨在引诱攻击者，以便他们的方法可以被分析，以增加真实网络的安全性。目前，越来越多的企业正在利用网络分段，并将其添加到他们的系统中，以增强其安全性。

尽管传统的外围安全有其积极的一面，但这种方法在防止特洛伊木马和计算机蠕虫在您的网络中传播方面并不完全可靠。传统上，为了对抗这种情况，会使用反病毒软件或入侵防御系统。他们可以检测并阻止这些攻击的传播。

此外，尽管该系统在防止外部威胁方面表现出色，但它在防止内部威胁方面并不有效。随着越来越多的人使用自己的设备远程工作，受污染的设备连接到公司网络的风险也在增加，这可能会给网络带来风险。这导致了零信任架构越来越受欢迎。

# 远程访问 VPN

VPN ( [虚拟专用网](https://www.safervpn.com/what-is-a-vpn))用于在最初是公共的网络上创建一个专用网络。这允许 VPN 的用户以相同的方式发送和接收数据，就像他们实际上连接到主专用网一样。这意味着任何通过 VPN 运行的应用程序都能够使用 VPN 所连接的专用网络的功能、安全和管理功能。

最初开发 VPN 技术是为了允许远程用户和不同的办公室分支机构访问主办公室分支机构网络上托管的应用程序和其他项目。要访问 VPN，用户必须通过使用密码或安全证书来验证自己。

当企业利用 VPN 技术时，它有助于确保远程员工和其他办公室能够建立到总部网络的安全连接，而没有攻击者通过远程用户渗透网络的风险。

# 网络分段

在计算机网络环境中，网络分段的实践是将计算机网络分成一组子网。这些子网中的每一个都称为一个网段。

![](img/d64cf77b3dbf46f6473ec295e561e585.png)

Photo by [Alina Grubnyak](https://unsplash.com/photos/ZiQkhI7417A?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/network?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

对网络进行分段的安全优势之一是来自分段的任何广播都将保留在内部网络中。因此，网络的结构只能在内部看到。

对网络进行分段的另一个好处是，如果网络的某个部分遭到破坏，攻击者的活动空间就会减少。此外，某些类型的网络攻击只在本地网络上起作用，这意味着如果你将系统的不同区域分段，根据它们的用途做出这些决定。例如，如果您要为您的数据库、web 服务器和用户设备创建单独的网络，这将有助于使您的网络更加安全。

网络分段还可以用来确保人们只能访问他们需要的资源。这将通过把你的资源有策略地分配到不同的网络，并把具体的个人分配到每个网段来实现。

正确使用网络分段来提高安全级别需要将您的网络分割成不同的子网，并给予每个子网一定级别的访问授权。然后，您应该采取措施，确保已经制定了一个协议来限制可以在每个子网之间传输的内容。

# 基于角色的访问控制

[基于角色的访问控制](https://www.techopedia.com/definition/23933/role-based-access-control-rbac) (RBAC)根据用户拥有的授权级别，帮助限制对某些系统的访问。拥有 500 多名员工的绝大多数公司都使用基于角色的访问控制，中小型企业也开始更多地使用这种技术。为了最有效地利用 RBAC，一家公司会将他们的用户档案按特定类别进行划分。一般来说，它们将基于工作角色、资历级别和基于前两个因素的每个人需要的资源。

例如，如果一个组织要使用 RBAC，而财务团队的一名初级成员要登录他们的网络，那么该员工将有权访问他们需要在其工作角色中查看的较低级别的财务数据。然而，他们的访问仅限于此。例如，他们将无法查看与法律团队相关的任何文件或数据，或者只能由高级财务团队成员(如财务总监)查看的文件。

当企业利用 RBAC 时，这是一种非常有效的方法，可以确保任何敏感数据仅被有权查看这些数据的个人查看。它还有助于防止故意的内部信息泄露。

![](img/aec64d5291ae939b377b6a98a74b6439.png)

Photo by [Jonathon Young](https://unsplash.com/photos/hYDBcGGXrUo?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/access-card?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

# 软件定义的边界(SDP)

**什么是软件定义的边界？**

在组织内创建零信任架构的方法之一是创建或使用 SDP。我们将了解什么是 SDP，这样您就可以做到这一点。

由于云存储在当今已经变得越来越普遍，这些云系统受到网络攻击的风险也越来越大，因为云服务器无法通过传统的外围安全措施来保护。这促成了 2013 年软件定义的边界的诞生。软件定义的边界是一个研究工作组。他们的重点是创建一个安全系统，帮助防止对云系统的攻击。

他们的任何研究成果都将免费提供给公众使用，不会受到任何使用费或任何其他限制。

从工作组成立之初，他们就决定尝试并专注于构建一个既经济高效，又非常灵活有效的安全解决方案。在他们的工作中，团队确定了三个基本的设计要求。

首先，他们决定他们的安全架构需要确认用户的 ID、他们使用的设备以及他们访问特定目录的权限。接下来，他们决定使用加密技术进行验证(这也是我们今天所知的区块链背后的基础技术)，这将是确保他们的安全协议得到应用的最佳选择。最后，我们决定实现前两个要求所需的工具是安全工具，这些工具有可靠的跟踪记录，并且在公共领域中。

SDP 决定他们的安全架构应该基于控制通道。这个控制通道将使用标准组件，该团队认为这些组件最适合该任务。这些组件是 SAML、PKI 和 mutual TLS。

工作组最终基于这一想法发表了一篇论文，以评估是否存在对这种系统的需求。这就是他们将其命名为软件定义的边界的地方。

人们对 SDP 的工作非常感兴趣，这促使他们在 2014 年 4 月发布了第一版系统。

他们有史以来的第一个设计是由一个启动主机组成的，它将向控制器提供关于正在使用什么设备以及由谁使用的信息。该信息将与相互 TLS 连接一起传输。一旦完成，控制器将链接到发行 CA 以确认设备的身份，并且还将链接到 ID 提供者，以便他们可以验证用户的身份。确认该信息后，控制器将提供一个或多个相互 TLS 连接，这些连接将链接前面提到的发起主机和任何所需的接受主机。该系统效果显著，能够防止任何类型的网络攻击，包括[中间人](https://en.wikipedia.org/wiki/Man-in-the-middle_attack)、 [DDoS](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/) 和[高级持续威胁](https://searchsecurity.techtarget.com/definition/advanced-persistent-threat-APT)。

# SDP 第一版的架构

最初用于商业用途的 SDP 产品是使用业务应用的覆盖网络实现的，例如远程访问高价值数据，或者保护云系统免受攻击。SDP 的发起主机采用客户端的形式，而接受主机成为网关。

![](img/d94ae40f2cb4860ddeb1789df715b954.png)

Photo by [Anastasia Dulgier](https://unsplash.com/photos/OKOOGO578eo?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/network-architecture?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

## SDP 客户端

SDP 客户端本身负责各种各样的功能。其中两项包括验证正在使用的设备和正在使用的用户 ID，以及将列入白名单的应用程序路由到已授权的受保护应用程序。

SDP 客户端具有实时配置，以确保相互 TLS VPN 连接仅链接到个人用户有权使用的项目。这意味着 SDP 客户端的功能是根据用户的权限级别限制对某些数据点的访问。这是在用户的 ID 和设备都经过验证后执行的。

## SDP 网关

SDP 网关充当到 SDP 客户端的相互 TLS 连接的终止点。在拓扑意义上，网关将被实现为尽可能靠近受保护的应用程序。

一旦请求访问的设备的身份被确认并且它们的许可级别被公开，SDP 网关将接收 IP 地址和它们的证书。

## SDP 控制器

SDP 控制器充当后端安全功能(如身份提供者和 SDP 客户端本身的认证机构)之间的可信中间人。一旦 SDP 客户端已经实现验证并且已经检查了用户的授权级别，SDP 控制器将开始配置 SDP 客户端和 SDP 网关，使得它们可以通过相互 TLS 建立实时连接。

## SDP 体系结构的安全特性

当您正确实施所有这三个特性时，SDP 架构可以为您的安全系统提供出色而独特的特性。下面列出了这些功能。

**(1)隐藏信息** 没有 DNS 信息，受保护的应用基础架构内也没有任何可见端口。因此，受 SDP 保护的资产被称为“黑暗”资产，因为即使您扫描它们，也无法发现它们。

**(2)预认证** 尝试访问的设备的身份总是在它们被允许连接之前被验证。设备的身份将使用嵌入 TCP 或 mutual TLS 架构中的 [MFA 令牌](https://searchsecurity.techtarget.com/definition/multifactor-authentication-MFA)来确认。

**(3)预授权** SDP 系统中的用户只被授予因其角色而需要访问的服务器的权限。用于确认身份的系统会将用户的授权传达给 SDP 控制器。这是使用 SAML 断言来实现的。

**(4)应用层访问** 即使用户被授权访问应用，这也只是在应用层而不是在网络层。SDP 还将主机正在使用的设备上的某些应用列入白名单，这有助于保持应用到应用级别的系统通信。

**(5)扩展性。** SDP 的架构建立在各种不同的基于标准的部件的基础上。这些包括相互 TSL、SAML 和安全证书。由于由基于标准的部分组成，SDP 架构可以轻松地与其他类型的安全系统链接和集成，包括数据加密系统和远程证明系统。

通过预认证和预授权的结合使用，企业可以创建对未识别主机不可见的网络，同时根据已知用户的组织角色，仅向已知用户提供必要的权限。

SDP 的一个关键部分是，在用户和受保护的应用程序之间建立 TCP 连接之前，需要进行预认证和预授权。除此之外，授权用户将只被授予对某些应用程序的权限，以确保受损设备无法在网络中横向移动。