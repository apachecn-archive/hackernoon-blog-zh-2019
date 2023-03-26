# 最佳匿名操作系统:比较巨头

> 原文：<https://medium.com/hackernoon/best-operating-systems-for-anonymity-comparing-titans-3501fd5cba3b>

![](img/4d56656dbc90b2a31e770cc4745e7c96.png)

有许多旨在实现在线匿名的操作系统。但是有几个是真的好呢？我认为不多。下面我想推荐几个 Linux 发行版，它们可以帮助解决许多隐私/匿名问题。我们走吧！

# Tails OS

Tails 是基于 Debian 的 Linux 发行版，旨在提供隐私和匿名。所有传出连接都通过 Tor 网络路由，所有非匿名连接都被阻止。该系统设计为从 Live CD 或 Live USB 启动，不会在使用它的机器上留下任何痕迹。Tor 项目是 Tails 的主要发起人。这个操作系统被新闻自由基金会推荐使用，也被爱德华·斯诺登用来揭露“T2 棱镜”。

为了评估 Tails 的所有优点和缺点，有必要深入了解这个操作系统的创建目的以及应该如何使用它。

这个操作系统可以很快启动。创建闪存驱动器后，将需要 1-2 分钟来访问互联网(如果您有良好的硬件)。然而，你不应该期望 Tails 有太多的功能。它允许您快速连接到 Tor 网络，使用信使并通过安全通道连接，生成并保存密码，以及清除元数据文件。

Tails 的核心任务是确保用户在网络上的匿名性和安全性，同时保持使用的便利性和易用性。它做得很好。整个系统在上传到 RAM 的实时模式下工作。Tails 未安装在固态硬盘或硬盘上。会话结束后，即使有人可以完全访问设备，也无法确定用户在计算机上做了什么。

不建议将此操作系统用作永久操作系统。关闭或重启系统后，所有下载的文件、浏览器历史记录等。—已删除。

可以创建一个永久加密分区，在上面存储密码和各种类型的文件，但是这些文件应该不是很敏感。

要运行 Tails，你需要一个至少 1GB 内存的设备和一个过时的处理器。尾部的最佳设备规格:8GB RAM 和双核处理器。

安装第三方程序不是这个操作系统的强项。在 Tails 上安装应用程序并不是最愉快的事情。即使每件事都做得很正确，也经常会出现无法预料的错误。可能发生的情况是，在多次重启后，您安装的软件可能会消失。如果您需要系统地使用第三方软件，最好的选择是创建自己的发行版来满足您的需求。

Tails 的目标是不留下任何痕迹，除了访问 Tor 网络和存储文件之外的任何事情都可能是个问题。最好使用 Tails 来快速访问网络、连接到远程 web 资源、处理文档、通过加密通道进行通信、发送/接收加密货币。

**尾巴优点:**

快速访问网络(Tor、即时信使、在线加密钱包)。

用于清理元数据的内置工具。

内置即时通讯工具。

密码的生成/存储。

几乎适用于任何硬件。

反面缺点:

安装困难。

第三方软件的安装问题。

不适合作为永久操作系统。

不适合存储高度敏感\私人文件。

Tails 是一个好系统。它有其缺点，但同样，它只是为特定的任务量身定制，并不总是对所有用户都有效。Tails 更关心的是匿名的问题，而不是安全性。当然，这是一个匿名的非常好的安全系统，但是还有其他更先进的发行版。由于斯诺登，Tails 广为人知，并因其简单而被许多社区宣传。

# **Whonix**

Whonix 是基于 Debian 的 Linux 发行版，以前称为 TorBOX。旨在通过 VirtualBox 和 Tor 确保匿名性。无论是恶意软件还是受损的超级用户帐户都不会导致 IP 和 DNS 泄漏。与此操作系统捆绑的所有软件都经过预配置，可以使用最高的安全设置。

Whonix OS 由两个虚拟机组成:Whonix 网关和 Whonix 工作站，通过一个隔离网络连接。网关仅通过 Tor 工作，并作为网络的网关，工作站在完全隔离的网络中工作。

所有网络连接只能通过 Tor 进行。工作站的唯一网络接入是网关。所有流量、所有应用和流程都将通过 Tor。

应用程序无法绕过 Tor 访问互联网。应用程序只能看到本地 IP 地址。无法跟踪时区，时钟被设置为 UTC，时间戳 HTTP 头被发送到随机选择的 web 服务器。

实现 Tor + VPN 的不同序列的可能性是该操作系统的一大优势。您可以配置系统，使所有流量首先通过 VPN，然后通过 Tor，最后再通过 VPN。

Whonix 是一个具有广泛的定制和配置可能性的系统，有时不能在 Tails 中完成。有许多程序和设置可以让你建立自己的匿名/安全系统，删除使用文件的痕迹，使用即时信使，处理不同的文件类型等。

对于匿名互联网访问来说，Whonix 无疑是一个很好的系统，但是持续使用它会有很大的问题。由于 Whonix 是围绕虚拟化构建的，这可能会导致一些问题。例如，在使用外部媒体时，您可能会遇到困难。如果你需要连接 u 盘，它会先经过主 OS，比如 Windows，再经过 VirtualBox，最后到达 Whonix 系统，而这并不是最安全的方式。

**Whonix 优点:**

高度匿名。

大量软件工具可供使用。

广泛的微调可能性。

**Whonix 缺点:**

不便携。

需要强大的硬件。

与 VirtualBox 绑定，如果安装了 VirtualBox 的操作系统遭到黑客攻击，会带来很大的风险。

速度不快，比其他操作系统需要更多时间访问网络(需要启动 VirtualBox、Gateway、Workstation)。

Whonix 是一个很好的辅助(附加)系统，因为它不可移植。便携性是这一领域最重要的标准之一。它还绑定到 VirtualBox，由于这不是一个活动的系统，如果不使用加密方法，很容易检测到 Whonix 的存在。

Whonix 应该只在特殊情况下使用。我把它放在我的列表中，因为它在设置方面非常灵活。

# **哥达吉**

Linux Kodachi 也是基于 Debian 的。Kodachi 的目标是提供最匿名和最安全的网络访问，并保护系统本身。所有流量都通过 VPN，然后通过带 DNS 加密的 Tor 网络。[免费 VPN](https://cooltechzone.com/free-VPN) 已经预先配置好了。

Kodachi 被定位为反取证操作系统，使得对驱动器和 RAM 的取证分析变得非常困难。

[科达奇选择 XFCE](https://www.xfce.org/) 作为桌面环境，系统设计与 MacOS 非常相似。系统和网络参数实时显示在桌面上，这使您可以监控系统，也可以监控 tor 和 VPN 网络的运行。

Kodachi 支持 DNScrypt，这是一种协议和实用程序，它使用椭圆加密技术加密对 OpenDNS 服务器的请求。它消除了许多典型的问题，如 DNS 泄漏和在提供商的服务器上留下网络活动的痕迹。

如果需要在 P2P 网络中隐藏 IP 地址，可以使用 PeerGuardian。如果您需要处理可疑的进程，可以使用名为 Firejail 的内置沙箱轻松隔离它们。一个很好的选择是能够快速改变 Tor 出口节点，并选择使用 Multi Tor 的特定国家。

Kodachi 有相当数量的预装软件可以解决任何任务，例如，加密信息(VeraCrypt，TrueCrypt)，发送机密消息(GnuPG，Seahorse，Enigmail，GNU Privacy Guard Assistant)隐藏痕迹(MAT，Nautilus-wipe，Nepomuk Cleaner，BleachBit)。

此外，Kodachi 还拥有自己的基于 Tor 浏览器的浏览器，其开发者在其中裁剪出了一些有问题的 Tor 模块。

Kodachi 是一个平衡的系统，它是一个强有力的工具，可以用来建立各种意义上的匿名和安全系统。该操作系统最好与存储高度敏感信息的加密介质结合使用。

在我看来，Kodachi 是目前最好的系统，它可以让你解决大量的任务。

**科达奇优点:**

快速启动(即像 Tails 一样快速访问网络)。

许多预装程序。

对硬件要求不高。

实际上没有缺点，但是它们可能出现在一些狭隘的任务\需求中。

还有其他一些很好的匿名操作系统，比如 Subgraph 和 Qubes。

# **量子**

Qubes OS 使用一个有趣的原理来启动应用程序。每个应用程序运行在单独的虚拟机上。应用程序根据重要程度进行分类。浏览器在一个虚拟机上运行，信使在另一个虚拟机上运行。对于用户来说，这两个程序似乎运行在同一个工作区。隔离应用程序意味着如果恶意软件进入，个人文件将不会受到损害。

Qubes 操作系统只有在安装到内部驱动器后才能工作，它没有活动模式。

# **子图**

子图操作系统背后的关键思想是在隔离的沙箱上运行定制应用程序。为此，使用了子系统 Oz。Oz 由一个接收创建沙箱请求的守护程序(系统服务)、一个 Xpra X-server 和一组特殊的实用程序组成。

子图 OS 是一个有点原始的工具。目前只有 alpha 版本可用。

子图和量子还不错，但还没好到可以放在领袖之列。子图 OS 太原始，Qubes 在设置方面太混乱。