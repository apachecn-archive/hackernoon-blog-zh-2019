# 在 x 战警的帮助下改进你的单元测试

> 原文：<https://medium.com/hackernoon/improving-your-unit-tests-with-help-from-the-x-men-a4eef1e50f25>

![](img/669470d3be81c5cd251c0adff6ac5650.png)

Photo by [Lena Rose](https://unsplash.com/@happilyabstract?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

如果我告诉你 x 战警可以让你成为一名更好的软件测试员，你会怎么想？他们不能，但是他们的超级恶棍威廉·史崔克可以。

这篇文章是关于如何使用突变测试来改进你的单元测试。有几个突变测试框架，但我将谈论的框架被称为 [Stryker](https://stryker-mutator.io/) ，这是以 x 战警中想要杀死所有变种人的超级恶棍命名的。我使用 Stryker 已经两年多了，在这两年中，我在三个大型企业项目中实施了 Stryker，并就该框架做了几次演示。

## 小心！

我想以一个警告开始这篇文章，突变测试不适合心脏虚弱的人。首先，它是乏味的，耗时的，并且经常拖延开发的测试阶段，经常需要开发人员编写更多的单元测试。为什么还要为此烦恼呢？因为这是确保单元测试真正提供价值的万无一失的方法。

每个开发人员都见过这样的单元测试，它看起来很棒，但实际上并不测试任何东西，或者只是为了提供代码覆盖率而存在。这些是突变测试暴露的测试。这是单元测试中的佼佼者，命运的选择，任何摇滚明星测试人员都不是真正的摇滚明星，除非他们有突变测试来检查他们的单元测试。既然你已经被警告了，让我们进入细节。

![](img/7bc999268dd8540c77fc888c212d4f9f.png)

Photo by [MAYANK D](https://unsplash.com/@mayank_dimri?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

# 什么是突变测试？

简单的一句话回答是*突变测试是为你的单元测试*而测试。这是什么意思？变异测试是通过一个框架完成的，比如 Stryker，它会变异或改变代码的特定部分，并检查这种变异是否会导致单元测试失败。如果突变体导致您现有的一个单元测试失败，那么这个突变体就被认为是“被杀死”了。在突变测试结束时，会生成一个报告，其中包含被杀死和幸存的突变体的完整列表，类似于您在使用 Jest 或 Jasmine 的代码覆盖报告中看到的内容。

## 简单的例子

假设您有一些为应用程序生成 URL 的代码。希望有一个单元测试来检查 URL 路径并确保它被生成。变异测试框架会进来，把你的端点变异成一个 null 或空字符串。你的单元测试会发生什么？如果失败了，那很好，这意味着你的测试足够聪明，知道 URL 应该是什么，变异体将被认为被杀死。如果你的单元测试没有失败，这意味着你的单元测试没有你想象的那么好。框架会将突变体列为存活的，你需要回到绘图板去写一个更好的单元测试。下面是一个字符串突变的例子:

```
String url = "deadpool.com"
goTo(url)//mutated code
String url = ""
goTo(url)
```

# 突变测试框架

Stryker 是一个开源突变测试框架，有一个非常活跃的开发社区。两年前我开始使用 Stryker 时，该框架仅适用于 JavaScript，但多年来它一直在不断发展，现在可用于 JavaScript、TypeScript、Scala 和 C#。它有一个 CLI 工具可用于快速简单的设置，并且可以很好地与 Jasmine 和 Jest 等常见测试框架配合使用。我也使用过 Java 的 [PIT Test](http://pitest.org/) ，突变测试的概念是一样的，但是框架更加基于控制台。虽然每个突变测试框架可能略有不同，但概念是相同的，重要的是开始使用一个。

![](img/cc1d03716ae21a573daf9cdfbb3d7017.png)

Photo by [Artem Sapegin](https://unsplash.com/@sapegin?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

# 变异测试利弊

当第一次开始使用突变测试的过程将会非常缓慢。杀死某些变种人可能很困难，而且不得不重写单元测试也不是什么有趣的事情。随着时间的推移，好处是值得的，就像生活中的任何事情一样，你练习得越多，这个过程就会变得越快。

## 专业的

*   更高质量的单元测试
*   不要再编写毫无意义的测试，这些测试只是为了提高一个度量标准(比如代码覆盖率)
*   对您的应用程序经过全面测试更有信心
*   更少的生产缺陷
*   捕捉到更多虫子
*   开发人员有机会收到关于他们单元测试质量的即时反馈
*   Stryker 并行运行，因此如果资源可用，它可以运行得非常快

## 骗局

*   在开发周期中增加一个额外的步骤
*   在具有四个或更少内核的机器上运行大型代码库可能需要一个多小时
*   如果 CLI 生成的配置不适合您的项目，那么配置可能很难确定

# 结论

在开发人员中，突变测试似乎仍然很少见，但希望这篇文章鼓励任何阅读的开发人员尝试一下。设置可能会很慢，杀死第一批变种人可能需要很长时间，但是杀死的变种人越多，这个过程就会变得越快。除了金刚狼提供单元测试辅导之外，Stryker 和 mutation testing 是你能找到的最接近 x 战警改进单元测试的方法。