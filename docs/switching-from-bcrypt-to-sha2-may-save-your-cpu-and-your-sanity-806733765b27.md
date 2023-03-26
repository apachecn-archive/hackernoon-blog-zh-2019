# 从 BCrypt 切换到 SHA2 可能会节省您的 CPU…和您的理智！

> 原文：<https://medium.com/hackernoon/switching-from-bcrypt-to-sha2-may-save-your-cpu-and-your-sanity-806733765b27>

![](img/e63d380424c7ad570332ab3d1462abc1.png)

现实是，数十亿的凭证已经被泄露或被盗，现在任何人都可以很容易地从网上下载。这些身份数据库中有许多包含明文形式的密码，而其他的则是单向散列的。单向散列法更好(我们马上就会知道为什么)，但是它只有在数学上可行时才是安全的。让我们来看看单向散列算法以及计算机如何处理它们。

# 散列法

根据定义，哈希是一种可以将任意大小的数据映射到固定大小的数据的函数。SHA2 是一种哈希算法，它对任意数量的字节使用各种逐位运算来生成固定大小的哈希。例如，SHA-256 算法产生 256 位的结果。该算法是专门设计的，因此从一个哈希返回到原始字节是不可行的。开发人员使用 SHA2 散列，因此他们不是存储纯文本密码，而是只存储散列。当用户通过身份验证时，他们在登录表单中键入的纯文本密码将被哈希处理，因为在相同的输入下，算法将始终产生相同的哈希结果，将该哈希与数据库中的哈希进行比较可以告诉我们密码是正确的。

# 破解密码

虽然单向哈希意味着我们不存储纯文本密码，但仍然可以从哈希中确定原始的纯文本密码。接下来，我们将概述反转散列的两种最常见的方法。

## 查找表

第一种称为查找表，有时也称为彩虹表。这种方法构建了一个庞大的查找表，将哈希映射到纯文本密码。该表是通过简单地散列每个可能的密码组合并将其存储在某种类型的数据库或数据结构中来构建的，以便快速查找。

以下是 SHA2 哈希密码的查找表示例:

使用查找表，攻击者只需知道密码的 SHA2 哈希，就可以知道它是否存在于表中。例如，让我们假设网飞使用 SHA2 散列存储您的密码。如果网飞被攻破，他们的用户数据库现在可能对任何有良好互联网连接和 torrent 客户端的人开放。现在，即使是一个普通的黑客也只需要查找与你的网飞账户相关联的 SHA2 散列，就可以知道它是否存在于他们的查找表中。这将几乎立即揭示你的纯文本密码是网飞。现在，这个黑客可以登录你的网飞账户，狂看《富勒之家》的所有四季(“多么粗鲁！”).他也可以在 Hulu 和 HBO Go 上尝试这个密码，看看你是否也为这些帐户使用了相同的电子邮件地址和密码。

防范这种攻击的最佳方式是使用所谓的 **salt** 。salt 只是一串随机字符，在哈希之前添加到密码中。每个密码应该有不同的 salt，这意味着查找表不可能有 salt 和密码组合的条目。这使得 salts 成为对抗查找表的理想防御手段。

下面是一个 salt 的示例，它是密码和 salt 的组合，然后经过哈希处理:

现在我们已经添加了 salt，我们实际生成散列的“密码”是字符串:

```
;L’-2!;+=#/5B)40/o-okOw8//3apassword
```

这个字符串很长，很复杂，包含许多随机字符。因此，创建查找表的黑客几乎不可能生成字符串的散列”；L'-2！；+=#/5B)40/o-okOw8//3apassword "。

## 蛮力

攻击者破解密码的第二种方法叫做暴力破解。这意味着攻击者编写一个计算机程序，该程序可以生成可用于密码的所有可能的字符组合，然后计算每个组合的哈希。如果密码是用盐散列的，这个程序也可以接受盐。然后，攻击者运行该程序，直到它生成一个与数据库中的散列相同的散列。这里有一个简单的破解密码的 Java 程序。为了保持代码简短，我省略了一些细节(比如所有可能的密码字符)，但是您已经明白了。

这个程序将生成长度在 6 到 8 个字符之间的所有可能的密码，然后对每个密码进行哈希运算，直到找到匹配的密码。由于可能的组合数量，这种暴力破解需要时间。

# 密码复杂性与计算能力

让我们使用 TI-85 计算器，看看能否算出这个程序运行需要多长时间。在本例中，我们假设密码只能包含 ASCII 字符(大写、小写、数字、标点)。这个集合大约有 100 个字符(我四舍五入是为了让数学更容易阅读)。如果我们知道密码中至少有 6 个字符，最多有 8 个字符，那么所有可能的组合都可以用这个表达式来表示:

```
possiblePasswords = 100⁸ + 100⁷ + 100⁶
```

这个表达式的结果等于**10101000000000000**。这是一个相当大的数字，更准确地说是 10 万亿分之几，但是对于我的程序运行来说，它实际上意味着什么呢？这取决于我运行的计算机的速度以及我的计算机执行 SHA2 算法需要多长时间。算法是这里的关键部分，因为程序的其余部分在创建密码时速度极快。

这就是事情变得危险的地方。如果你在谷歌上快速搜索[最快的比特币平台](http://lmgtfy.com/?q=fastest+bitcoin+rig)，你会发现这些机器是根据它们每秒能执行的哈希数来排名的。大一点的可以高达**44/s**。这意味着它每秒可以生成 44 万亿次哈希或**440 亿次**。

现在，如果我们将密码总数除以我们每秒可以生成的哈希数，我们得到的是比特币钻机为所有可能的密码生成哈希所需的总时间。在上面的例子中，这相当于:

```
bitcoinRig = 4.4e13
possiblePasswords = 100⁸ + 100⁷ + 100⁶ = 1.0101e16numberOfSeconds = possiblePasswords / bitcoinRig = ~230
numberOfMinutes = numberOfSeconds / 60 = ~4
```

这意味着使用这个示例比特币平台，我们可以在大约 4 分钟内生成长度为 6 到 8 个字符的密码的所有哈希。感到紧张了吗？让我们添加一个额外的字符，看看散列 6 到 9 个字符之间的所有可能的密码需要多长时间。

```
bitcoinRig = 4.4e13
possiblePasswords = 100⁹ + 100⁸ + 100⁷ + 100⁶ = 1.010101E18numberOfSeconds = possiblePasswords / bitcoinRig = 22,956 
numberOfMinutes = numberOfSeconds / 60 = ~383
numberOfHours = numberOfMinutes / 60 = ~6
```

通过在密码的潜在长度上增加一个字符，我们将总计算时间从 4 分钟增加到了 6 小时。使用暴力策略，计算时间增加了近 100 倍。你可能知道这是怎么回事——要打败暴力策略，你只需要让计算所有可能的密码组合变得不可能。

让我们疯狂一下，跳到 16 个字符:

```
bitcoinRig = 4.4e13
possiblePasswords = 100¹⁶ + 100¹⁵ … 100⁷ + 100⁶ = 1e32numberOfSeconds = possiblePasswords / bitcoinRig = 2.27e18
numberOfMinutes = numberOfSeconds / 60 = 3.78e16
numberOfHours = numberOfMinutes / 60 = 630,000,000,000,000 or 630 trillion
numberOfDays = numberOfHours / 24 = 26,250,000,000,000 or 26.25 trillion days
numberOfYears = numberOfDays / 365 = 71,917,808,219 or 71.9 billion years
```

总结我们的结果，如果我们采用这些表达式并简化它们，我们可以建立一个方程，解决任何长度的密码。

```
numberOfSeconds = 100^lengthOfPassword / computeSpeed
```

该等式表明，随着密码长度的增加，暴力破解密码的秒数也会增加，因为计算机执行哈希算法的速度是一个固定的除数。密码复杂度(长度和可能的字符)的增加称为**熵**。随着熵的增加，暴力破解密码所需的时间也会增加。

# 这些数学是什么意思？

问得好。答案如下:

> 如果您允许使用短密码，这使它们更容易记住，您需要减小 **computeSpeed** 的值，以保持一定的安全级别。
> 
> 如果您需要更长的随机密码，比如由密码生成器创建的密码，您不需要做任何更改，因为 **computeSpeed** 的值变得不那么相关了。

让我们假设我们将允许用户选择短密码。这意味着我们需要减少 **computeSpeed** 值，这意味着我们需要减慢散列的计算。我们如何做到这一点？

安全行业解决这个问题的方法是继续增加算法的复杂性，这反过来又导致计算机花费更多的时间来生成单向散列。这些算法的示例包括 BCrypt、SCrypt、PBKDF2 等。这些算法专门设计用于使计算机的 CPU/GPU 花费过多的时间来生成单个哈希。

如果我们能够将 **computeSpeed** 值从 **4.4e13** 降低到更小的值，比如**1000**，那么我们计算 6 到 8 个字符长度的密码的时间就会变得更短。换句话说，如果我们可以降低计算机的速度，使它生成每个哈希需要更长的时间，我们就可以增加计算所有可能的密码所需的时间。

```
computeSpeed = 1e3
possiblePasswords = 100⁸ + 100⁷ + 100⁶ = 1.0101e16numberOfSeconds = possiblePasswords / computeSpeed = 10,101,000,000,000 or 10.1 trillion
numberOfMinutes = numberOfSeconds / 60 = 168,350,000,000 or 168.35 billion
numberOfHours = numberOfMinutes / 60 = 2,805,833,333 or 2.8 billion
numberOfDays = numberOfHours / 24 = 116,909,722 or 116.9 million
numberOfYears = numberOfDays / 365 = 320,300
```

还不错。通过降低哈希计算的速度，我们将使用比特币平台的时间从 4 分钟增加到了 320，300 年。在这个比较中，您可以看到使用 SHA2 和 BCrypt 之间的实际差异。与 SHA2 和其他更传统的哈希算法相比，BCrypt 的速度非常慢。

安全行业多年来一直在争论这个问题:

> 我们是否允许用户使用短密码，并在合理安全的情况下让计算机承担生成散列的负担？还是我们强迫用户使用长密码，而只使用像 SHA2 或 SHA512 这样的快速散列算法？

一些业内人士认为，消耗大量 CPU 和 GPU 周期来计算密码散列已经足够了。通过强制用户使用长密码，我们获得了大量的计算能力，并可以通过关闭 42 台服务器来降低成本，我们必须运行这些服务器来跟上登录量。

其他人声称这是一个坏主意，原因有很多，包括:

*   人类不喜欢改变
*   像 SHA2 这样的简单算法的风险仍然太高
*   简单的算法目前可能容易受到攻击，或者将来可能会发现新的攻击

在撰写本文时，仍然有许多简单的算法没有受到攻击，这意味着没有人想出一种方法来减少计算每个可能的散列的需要。因此，在长密码上使用简单算法是安全的，这仍然是一个安全的断言。这使得不强迫用户使用长密码的唯一原因是上面提到的第一个原因，“人类不喜欢改变”。在现实中，许多用户会改变，有些人已经在使用长密码。

# 我们的新想法:让我们折中一下

作为身份管理解决方案的提供商，我们理解这场争论的双方。我们还强烈希望在大规模降低密码散列成本的同时维护安全性。这是一个我们在办公室一直在辩论和讨论的想法。如果我们根据密码的长度(以及可能的复杂性)动态地改变 FusionAuth 用来散列密码的算法，会怎么样？这是否可以将平均 CPU/GPU 消耗降低到足以产生影响的程度？

下面是一个算法的超级简单的示例代码，该算法仅基于密码长度来选择哈希方案:

当然，这只是冰山一角，我们可以对密码进行大量分析，并根据其他因素计算熵。这将允许我们选择一个保持高度安全性的散列，同时尽可能降低 CPU 成本。

让我们再一次重复上面的数学。

```
// Passwords of length 16 using SHA2
totalYears to generate all passwords = 71,917,808,219 or 71.9 billion years// Passwords of length 8 using BCrypt
totalYears to generate all passwords = 320,300 years
```

有趣的是，密码的长度比算法更能决定安全级别。

我们认为这个想法有可取之处。随着越来越多的人开始使用带有密码生成器的密码管理器，或者让浏览器为您生成一个唯一的密码，我们可以动态地选择一个可以显著降低 CPU/GPU 利用率的哈希。

值得思考的是，我们可以使用 PBKDF2 在类型为 **t2.medium** 的 Amazon EC2 实例上每秒散列大约 20 个密码。如果你是 Pokémon Go，尝试认证一半的已知世界，这样他们就可以抓住 Charizard，你认为需要多少 EC2 实例来处理他们的负载？有一个真正的商业案例可以改变业界对安全密码哈希的看法。

敬请关注即将发布的一篇博文，在这篇博文中，我们将展示 1 亿名密码长度不同的用户的真实性能数据。

FusionAuth 默认使用 **PBKDF2** 和**24000**次迭代作为默认密码哈希方案。BCrypt 和其他几种算法支持密码迁移。我们继续研究新技术，以降低 CPU 开销，同时保持安全密码存储的最高标准。

如果你想讨论这个功能，请在下面评论或访问 FusionAuth GitHub 问题，并投票或评论。[功能:基于熵的密码哈希](https://github.com/FusionAuth/fusionauth-issues/issues/85)

*这个最初发布在 FusionAuth 博客这里:*[*https://fusion auth . io/blog/2019/02/21/save-a-CPU-ditch-bcrypt-use-sha2-instead*](https://fusionauth.io/blog/2019/02/21/save-a-cpu-ditch-bcrypt-use-sha2-instead)