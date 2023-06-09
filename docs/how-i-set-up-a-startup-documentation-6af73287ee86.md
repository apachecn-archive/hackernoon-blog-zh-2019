# 我如何设置启动文档

> 原文：<https://medium.com/hackernoon/how-i-set-up-a-startup-documentation-6af73287ee86>

![](img/f5e97ad4bdd57f7fa04b89a22e7dfb2c.png)

From: [https://dribbble.com/shots/3807778-Swinging-Cat](https://dribbble.com/shots/3807778-Swinging-Cat)

> S **软件文档**是伴随计算机**软件**或嵌入源代码的文字或插图。它要么解释它如何操作，要么解释如何使用它，对不同角色的人可能意味着不同的东西。**文档**是**软件**工程的重要组成部分。[https://en.wikipedia.org/wiki/Software_documentation](https://en.wikipedia.org/wiki/Software_documentation)

## 阶段 0——Google docs plus 将功能保留在我的脑海中

![](img/d1dda82d4c5f250277f40bb6618624af.png)

当只有一个人给你的项目编码时，这很容易。
主要问题——每次我想写新东西时:
a)我应该打开我的 Gmail
b)然后去谷歌文档
c)然后我应该选择保存所有数据的文件夹，
d)打开我的文档

**缺点**

*   有点不可收拾。
*   如果你想和别人分享一个链接，你应该生成一个可分享的链接，复制并发送它。
*   有些人没有谷歌账户(疯狂吧？).这也是一个问题。
*   内容没有被网络蜘蛛索引，所以没有人可以意外地找到它。
*   没有很酷的搜索(至少我主要用它来搜索标题)
*   当你处理一个大文档时，你需要自己创建一个目录。

**链接**:[https://www.google.com/docs/about/](https://www.google.com/docs/about/)

# 开源代码库

![](img/d686cee47d72a7dd87b9e35e90686fe6.png)

## 第一阶段

我将我的代码和文档/文件保存在主要的 GitHub 存储库中。

**缺点**
很多乱七八糟的东西，因为它是用来存储你的代码的。有时候把所有东西都放在一个地方是非常紧迫的。
难以搜索。你需要记住你把它放在哪里。

**链接**:[https://github.com/](https://github.com/)

## 第二阶段

我没有在 markdown files 制定开发计划，而是将一些任务转移到 GitHub issues，添加标签和里程碑。

如果你仍然独自工作，这是一个很好的方法。但是当一个项目增长时，你会被淹没。像我一样。我有一大堆问题。很难快速管理。但是最好在 Github 上有一个文档化的问题，而不是存储在内存或文件中。

我只为文档创建了几个独立的存储库。因为我还是一个人，所以我只是移动了所有没有任何结构的文件。

缺点:它看起来仍然不像是合适的文档。没有人能浏览它，我用不同的语言存储内容，等等。

**第四阶段**

![](img/fb56658c13aecd670122c306536d823e.png)

Github 有一个很好的文档工具——pages/wiki。这是个好主意，但对我来说效果不好。不知道为什么。也许在那里共享和存储数据需要很多时间。我觉得对很多人都可以。维基不需要太多的技术知识来开始工作。

**缺点**
难以上传图片/截图。但是！这对我们来说是个机会。
我创建独立的存储库，将所有资产保存在一个地方。
因此，徽标、品牌手册、数据库模式存储在*“创意”*存储库中。这也是与设计师分享信息的好方法。我让人类更容易导航。当我需要分享一些东西时，我只需去那个存储库复制一个 URL。

**链接**:[https://pages.github.com/](https://pages.github.com/)

## 第 5 阶段— Gitbook

![](img/7852564f6f2a041661d336ad69b8b38a.png)

非常酷的产品。我喜欢。它与 Github 同步。
而且很好看。适用于降价格式。

**缺点**

*   它有一些用户界面问题。比如它有一个定制的在线编辑器，又名 draft.js
*   而且怎么给子页面添加交叉链接也不是很直观。如果你想做，你需要做 2-3 步。同样，它看起来不错，有更多我没有探索的特性，比如 slack 集成

最好将不同范围(文档的各个部分)的数据分开。因为如果你有 3 个主页，每个主页有 10 个子页面——在不同部分之间导航或拖动页面会很困难。对于不编码的人来说，这绝对是一个好方法。

我为什么离开它？他们完成了他们的 beta 测试，并引入了他们的付费计划，我们现在负担不起。所以是时候采取新的行动了。

**链接**:[https://www.gitbook.com/](https://www.gitbook.com/)

在第 3-4 阶段的某个时候，我读到了亚马逊开发方法。
简单地说——用简单的句子解释释放会产生什么结果。我建议你多读一些这方面的内容。**链接**:[https://www . quora . com/What-is-Amazons-approach-to-product-development-and-product-management](https://www.quora.com/What-is-Amazons-approach-to-product-development-and-product-management)

## 当前阶段

这不是一个线性的过程，所以我们仍然停留在先前阶段的一些文档上。现在我们把所有东西都搬到 Docusaurus。

我喜欢它是脸书发明的工具。它是免费和开源的。它与 React 一起构建，因此我们可以在必要时调整代码。
类似于 Gitbook —与 Markdown 一起使用。但更多的是针对编码员。
或开发人员应该设置它，经理只会与内容。
通过 markdown 格式，你也可以在 Github 上阅读/查看文件。
它在 GitHub 页面上也很好用。你只需要把它部署在 *gh-pages*
上，你就会有一个独立的包含 SEO 内容的 URL，可以吸引更多人关注我们的项目。

**链接**:

*   [https://docusaurus.io/en/](https://docusaurus.io/en/)
*   [https://docusaurus.io/docs/en/installation](https://docusaurus.io/docs/en/installation)
*   [https://docusaurus.io/en/users](https://docusaurus.io/en/users)

## 摘要

文档是开发过程中非常重要的工具，你应该尽可能多地使用它。如果你有长时间的会议、一对一的谈话、长时间的聊天——那么你需要尽快改善它。

我还是不觉得这是我们“进化过程”的终点。一个主要的目标是增加模块性，并引起更多的关注。我们仍然只在必要时才使用它。我们不是“更新文档文件->与团队成员共享数据”，而是“进行长时间的对话，然后将我们的一些意见复制到文档中以备将来之需”。

如果你想知道我是如何管理我的项目的，请在这里阅读:[https://medium . com/quick-code/how-I-manage-my-projects-c 17 c 78 c 796 c 4](/quick-code/how-i-manage-my-projects-c17c78c796c4)

喜欢就鼓掌(不然我就删了你的 facebook 账号)

![](img/0ecd8a9ecd6cf0385f56d9bb85b1b184.png)

From: [https://dribbble.com/shots/3005865-Moustached-nanny](https://dribbble.com/shots/3005865-Moustached-nanny)