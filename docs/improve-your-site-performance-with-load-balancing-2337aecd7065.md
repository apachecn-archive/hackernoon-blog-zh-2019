# 通过负载平衡提高您的站点性能

> 原文：<https://medium.com/hackernoon/improve-your-site-performance-with-load-balancing-2337aecd7065>

![](img/4e0559e59d87cc3f77427ded5c6fb340.png)

网络用户的期望每年都在增加，搜索引擎也非常重视确保网站为访问者提供无缝体验。这很大程度上是为了确保你的网站在任何设备上都易于浏览，并且便于导航，但这只是等式的一部分——你还需要为所有的访问者提供快速的浏览体验，即使是在流量突然激增的时候。这可能会带来一个问题。去年，谷歌开始推出一种算法，可以惩罚加载速度不快的网站，因此那些无法适应的网站注定会看到自己的排名和流量下降。用户也更加重视网站的加载速度，如果你的网站运行缓慢，他们会毫不犹豫地转向你的竞争对手。幸运的是，有一些[方法可以提高你的 WordPress 站点](https://www.shoutmeloud.com/speed-up-wordpress.html)的速度，并确保它能够处理尽可能多的流量。

根据 Petra Gems 的说法，当购物者试图在他们的钻石搜索过滤器页面上[购买散装钻石](https://www.petragems.com/diamonds)时，除了用户体验/界面之外，加载速度和网站的一般速度在进行转换或增加反弹之间产生了很大的差异。提高移动设备的速度对他们来说也很重要。总的来说，对他们来说，在决定移除重要的信任因素/印章和聊天工具与提高速度之间，这是一个艰难的妥协。他们选择了后者。

也就是说，您可以使用负载平衡来帮助您充分利用您的托管服务器，并以一种在用户体验方面最有意义的方式优化它们的性能。

# 什么是负载平衡？

![](img/83f77153440fd42d06a65a437ae8b817.png)

本质上，负载平衡是优化主机服务器使用的过程，以最大限度地提高性能并确保快速加载。

[负载平衡软件](https://perfops.net/flexbalancer)解决方案可以将传入流量导向不同的服务器，将访问者分散开来，以便每台服务器都能公平分担负载，并以最佳水平运行。

通过在多台服务器之间分配工作，您可以确保没有服务器过载，并且您的网站总是为来自世界各地的访问者快速加载。

如果没有这样的系统，即使您有足够数量的服务器来处理您获得的流量，也可能不够，因为服务器不一定能够按比例共享流量，其中一些服务器可能会过度扩展。

您能够在站点上实现负载管理的第一个要求是拥有多台服务器来托管您的站点——毕竟，如果您只有一台服务器，就没有理由管理流量负载，因为无论如何只有一个选项。

但这无论如何都是有意义的——如今，您不能只依赖于一台服务器，因为即使是一次简单的中断也可能成为您业务的重大挫折。

# 负载管理方法的类型

即使负载管理背后的基本原则保持不变，也有一些不同的方法可以用来更有效地分配站点的流量。

下面就让我们来探究一下。

## 最少连接

![](img/7017d27e317e175893f33c70e1f787c0.png)

第一种方法基于最少连接规则，这意味着服务器自动将访问者发送到当时最少使用的服务器。这确保了没有服务器完全空闲，并且由于任何给定服务器的低瞬时负载，允许实现高加载速度。

## 一系列

![](img/68713da9c37a92ba196d75a3929855e5.png)

第二种方法在操作方式上也很简单，但如果您希望确保每台服务器都获得公平的流量份额，这也是一个不错的选择。循环法不是将此时工作最少的服务器分配给访问者，而是尝试始终在所有服务器之间平均分配流量，并忽略任何其他性能指标。

## 预测节点

![](img/57979c14d1778eb69f65ca53b617f981.png)

最后，预测节点法是您可以选择的最先进的方法，它使用随着时间的推移积累的数据来获得洞察力和分析趋势，然后用于以可能产生最佳整体性能的方式分配流量。

虽然这种方法可能更复杂，但有解决方案可以处理它，并且随着时间的推移，结果可以提供最佳性能，即使当您的站点有大量流量时。

# 负载平衡的优势

既然我们已经介绍了什么是负载平衡及其不同的实现方法，我们可以探讨为什么您应该考虑在您的网站上使用负载平衡。

因此，以下是您将能够获得的一些最显著的优势:

## 提高装载速度

正如我们在整篇文章中提到的，在你的网站上安装负载平衡系统的最大好处是能够以最有效的方式处理网站流量。

您不必担心销售或其他重要活动期间的流量激增，您可以放心，系统会找到最有效的方式来处理访问者，并将他们引导到能为他们提供最佳性能的服务器。

由于谷歌也高度重视为你网站的访问者提供快速和不间断的体验，负载平衡所能提供的一致速度变得更加重要。

## 无需停机即可处理服务器维护

每个人都讨厌来到一个网站，只是为了了解它正在进行维护。

如果你经营的是一家小型电子商务商店，你或许可以在夜间或流量较少的时段更新服务器，但如果你经营的是一家拥有全球受众的大型网站，避免中断是不可能的。

然而，在负载平衡的帮助下，这个问题变得不存在-当服务器维护时间到来时，您可以在更新时简单地关闭每台服务器，将流量导向其他服务器，并确保您的网站始终可用。

# **轻松处理突发问题**

我们讨论了负载平衡如何有助于防止计划维护工作期间的中断，但是当您需要处理意外问题时，它可能更加重要。毕竟，通过定期维护，您至少可以选择在流量最少的时候更新服务器，但是最大的问题通常发生在流量最大的时候，这可能是最具破坏性的。即使你使用最好的 [WordPress 安全插件](https://optinmonster.com/wordpress-security-plugins/)，你的网站有时也可能屈服于攻击，除非你有办法保护你的服务器。

负载平衡解决方案还可以让成千上万的玩家在一台服务器上玩反恐精英和 PUBG 等游戏。我们可能会担心什么是[cs go](https://gadgetgang.com/best-headset-for-cs-go/)的最佳耳机，但负载平衡解决了这里的真正问题。今天的负载平衡可以监控每台服务器的性能，并在发现问题时及时做出调整。这样，无论何时出现问题，你的流量都会被简单地重定向到正在工作的服务器上，这样你就可以知道你的站点正在顺利地工作，直到。