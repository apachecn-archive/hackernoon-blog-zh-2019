# 在推出新软件之前测试的 227 项质量保证清单

> 原文：<https://medium.com/hackernoon/the-definitive-227-item-quality-assurance-checklist-to-test-before-launching-new-software-48a624574f35>

![](img/e234027b47bb5bb4ba32d8930faa2eb4.png)

Credit: [Samule Sun](https://unsplash.com/@samule?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

你有一个惊人的想法…

你搞定了 UX…

你有一个漂亮的用户界面…

你已经准备好开始开发你的应用了。

有趣、刺激和探索阶段已经结束，你正进入执行模式。你想要令人难以置信的用户体验，让你的应用成为下一个大事件。需要什么？测试，测试，测试…

# 需要提前考虑的事情(在你开始开发之前)

测试和质量保证(QA)是一项耗时且有时枯燥的任务。但是，为了推出用户喜欢的应用程序，进行深入测试是至关重要的💖。

在开始开发应用程序之前，请考虑以下几点:

*   应用需要支持哪些**平台**？网络、移动、平板、桌面？
*   **Web:** 需要支持哪些浏览器？Chrome、Firefox、Safari、Internet Explorer、Edge 等。？
*   **手机&平板:** iPhone 和/或 Android？iPad 和/或其他平板电脑？
*   **桌面:** Windows app 和/或 Mac app？
*   **兼容性:**是只支持最新发布的 OS 和浏览器版本，还是需要兼容旧版本？

假设你需要支持 5 个浏览器+ iPhone + Android，你需要向后兼容所有平台，并支持不同的设备；然后您将看到测试工作是如何快速扩展的。

# 整体测试方法

遵循以下 5 个技巧来加速测试并快速找到关键错误:

1.  执行跨平台测试:在所有支持的平台上同时使用不同的用户登录。使用模拟器和物理设备。您现在可以开始测试了。
2.  检查最重要的功能、整体流程等。变化，组合，细节和边缘情况可以稍后检查。
3.  做一切你认为不应该被允许做的事情！
4.  想办法让系统崩溃！！
5.  当然，检查拼写，用户界面，设计，对齐等。

你当然可以用模拟器做很多测试。但是记住也要在物理设备上测试。它们有时会提供略微不同的结果😉

# 深度质量保证测试

这里有一份在你当前或下一个项目中需要注意的事情的详细清单。

这是所有参与你的应用程序开发的成员的清单。开发者(后端+前端)，设计师(UX + UI)，QA，QC，项目经理，产品负责人，支持。

1.  **注册:**用邮箱创建账户。
2.  注册:通过电子邮件中的链接激活帐户。
3.  注册:创建密码。哪些规则适用于密码？小写和大写字母、数字和特殊字符、最小长度等。
4.  **登录:**成功登录。
5.  登录:打开应用时自动登录。
6.  登录:使用不正确的用户名和/或密码登录失败。
7.  登录:在太多不正确的登录尝试时锁定帐户。
8.  登录:重新激活帐户，如果它已被锁定。
9.  登录:测试社交登录，如脸书、谷歌、LinkedIn 等。
10.  登录:测试单点登录。
11.  登录:测试双因素身份验证。
12.  **注销:**从应用程序中注销。
13.  注销:注销所有设备。
14.  **简介:**修改密码。
15.  **忘记密码:**验证您是否收到了密码重置电子邮件或短信代码，以及更新后的密码是否能正常工作。
16.  **入职:**测试流程的所有变化。例如，入职是否根据选择分成不同的路线，是否可以选择不同的模板/组等。
17.  入职培训:如果用户需要选择最少数量的主题进行跟进，请检查您是否无法继续。
18.  Onboarding: 如果用户在流程中间停下来会怎么样？
19.  入职:注册后测试电子邮件入职顺序。也许你用的是[滴滴](https://www.drip.com/)、 [Mailchimp](https://mailchimp.com) 或者 [ActiveCampaign](https://www.activecampaign.com) 之类的服务？
20.  **空状态:**当没有内容显示时，应用程序看起来是否正常？添加第一项时会发生什么？
21.  空状态:删除所有内容并检查空状态。
22.  **常规:**应用程序中的每个字段都是正确的类型吗？单行文本、多行文本、数字、是/否、下拉列表、选择、查找、日期、时间、人员、计算值、链接等。
23.  常规:该字段是可编辑的还是仅可查看的字段(为编辑而锁定)？
24.  常规:字段有最小或最大长度吗？它需要精确的字符数吗(就像你需要提供精确字符数的信用卡细节)？
25.  常规:突出显示所选字段。
26.  常规:在字段中显示提示文本。添加第一个字符后隐藏。如果字段中的所有字符都被删除，则再次显示提示文本。
27.  常规:自动大写文本字段。
28.  常规:测试字段是否区分大小写。
29.  常规:使用特殊字符，如&、'、%、？等。
30.  一般:尽量在所有字段中添加空格。
31.  常规:空白/空字段可以吗？如果你插入一个空格并试图保存呢？
32.  常规:提前输入，是否提供建议？
33.  常规:复制/粘贴文本、超链接和电子邮件地址。
34.  一般:尝试添加表情符号(例如通过从[www.getemoji.com](http://getemoji.com/)复制/粘贴)。
35.  常规:尝试在下拉列表和时间选择器字段中键入文本。
36.  常规:当您应该只能选择一个值时，您可以选择多个项目，反之亦然。
37.  常规:设置过去的日期。设定未来的日期，例如明年。
38.  常规:在字段下方显示帮助文本。
39.  常规:显示验证规则(例如，创建密码时)。
40.  常规:项目是否实时更新？
41.  常规:什么时候应该截断长文本？
42.  概述:验证动态计算是否正确，如使用的存储、可用的剧集数量等。
43.  概述:测试导航。例如，取消、后退一步、点击弹出窗口外部等。
44.  常规:检查错误消息。
45.  概述:从您离开的地方开始(记住上一个状态)。例如，你最后打开了哪个页面、你最后查看了哪个文档、你已经收听了播客的多长时间等等。
46.  常规:检查联机/脱机状态是否正确显示。尝试在几个设备上联机，然后一个接一个地关闭，直到不再连接。
47.  常规:检查共享是否按预期工作。
48.  一般:关注/喜欢可以不关注/不喜欢吗？是否为其他用户动态反映。
49.  常规:如果有相互依赖的字段，请检查业务规则。例如，如果一个字段中填充的值缩小了下一个字段中可用的选项。返回并更改先前的字段。验证相关字段是否已更新/清除。
50.  常规:检查隐藏字段的业务规则，直到在上一步中填充了特定值。
51.  **新建:**创建一个新项目。
52.  新:一个接一个地快速添加新项目。
53.  新建:复制现有项目。
54.  **更新/编辑:**更新项目并保存。
55.  更新/编辑:尝试在字段中添加不正确的输入(例如，在数字字段中添加字母)。
56.  更新/编辑:验证数据是否正确保存，并在您再次打开项目时显示。
57.  更新/编辑:修改多个字段(在一些字段中添加内容，在另一些字段中删除，在一些字段中修改)并验证数据是否正确保存。
58.  更新/编辑:拖放以更新项目。
59.  更新/编辑:更改图标。
60.  更新/编辑:选中同时编辑，两个用户同时登录并编辑同一个项目。
61.  更新/编辑:你能存档一个项目吗？
62.  更新/编辑:批量更新项目(例如，如果您的组织名称发生变化，您需要更改系统中的所有元数据)。
63.  更新/编辑:如果您有一个锁定的项目(例如，批准的文档)，一些元数据是否“不太重要”允许您编辑它们？示例:再次假设文档已经标记了您组织的名称，并且您想要更新它。
64.  **删除:**删除一个项目(或者离开一个群)。
65.  删除:验证已删除的项目是否被实时删除。
66.  删除:恢复已删除的项目。
67.  删除:永久删除项目。
68.  **多个项目:**上传多个项目/文件/图像。在后台显示微调器、进度条或上传，以向用户指示进度。
69.  多个项目:选择多个项目。
70.  多个项目:移动多个项目。
71.  多个项目:删除多个项目。
72.  **弹出窗口(模态):**在必填字段中添加文本→创建/保存按钮变为活动状态。
73.  弹出窗口(模式):删除必填字段中的文本→创建/保存按钮变为非活动状态。
74.  弹出窗口(模态):当在弹出窗口之外点击时，弹出窗口应该被关闭，内容被保存还是应该保持打开？
75.  **文本&消息:**如果没有输入文本，尝试保存/发送。
76.  短信:发送单行文本。
77.  文本和消息:发送长消息(例如+256 个字符)。
78.  文本和消息:使用 SHIFT+Enter 换行符。
79.  文本和信息:发送表情符号。
80.  文本和消息:如果用户添加多行，是否扩展字段？领域应该能扩展到什么程度？
81.  文本和消息:在现有文本的开头、中间和结尾添加光标。然后添加一些新的文本。现有案文必须保留。
82.  文本和消息:在现有文本的开头、中间和结尾添加光标。然后粘贴一些文本。现有案文必须保留。
83.  文本和信息:在文本中间添加表情符号——现有文本必须保留。
84.  文本和信息:当其他用户输入时提示。
85.  文本和消息:指示消息是否被阅读。
86.  文本&消息:跨平台表情符号的正确渲染。
87.  文本和信息:表情符号的 Unicode 转换。
88.  **图片:**添加图片。
89.  图像 **:** 包括不同分辨率和图像比例的预览图像。
90.  图像:放大/缩小。
91.  图像:在图像之间快速滑动。
92.  图像:绘制，操作，旋转和保存更改。
93.  图像:删除图像。
94.  **文件:**上传所有类型的文件(doc、docx、xls、xlsx、jpg、png、pdf、mp4、zip 等。).
95.  文件:上传小文件和大文件。
96.  文件:上传不同 URL 编码的文件。
97.  文件:打开和预览所有文件类型(或定义的子集)和不同的 URL 编码。
98.  文件:下载所有文件类型。
99.  文件:重命名文件。测试包含特殊字符如'的文件名。
100.  文件:作为新版本上传。
101.  文件:上传和替换现有文档，或者避免同名的当前文档被覆盖。
102.  文件:添加文件夹和子文件夹。
103.  文件:导航(展开/折叠)文件夹和子文件夹。
104.  文件:重新排列文件夹和嵌套文件夹。
105.  文件:检查文档版本(次要和主要版本)。
106.  文件:从其他文件类型创建 PDF 版本。
107.  文件:打印文件或锁定生成的 PDF 副本进行打印。
108.  **链接:**收到的链接可以点击。
109.  链接:检查所有链接的预期工作。
110.  **视频:**录制并添加视频。
111.  视频:播放/预览视频。
112.  **通话:**检查语音、视频、屏幕共享等功能，并接管控制权。
113.  通话:检查麦克风无法取消静音的问题。我们过去经常遇到这种情况，例如在使用 Skype 进行商务活动时，客户可以听到我们的声音，但我们却听不到他们的声音。迫使客人离开并重新连接；并最终通过电话呼叫。
114.  **表格:**测试从第一步到最后一步的流程。
115.  形式:测试流程中的所有环回。
116.  表单:是否应该锁定前面的步骤进行编辑？何时重新打开进行编辑？
117.  **工作流程:**测试主要流程，在该流程中，您仅选择积极的结果。
118.  工作流:用所有回环测试所有主要流程。
119.  工作流:在一个工作流正在运行时启动另一个工作流。
120.  工作流:终止工作流。
121.  **电子签名:**需要用户名和密码吗？
122.  电子签名:拒绝后会发生什么？
123.  电子签名:批准后会发生什么？
124.  **审计跟踪:**查看审计跟踪。
125.  审计跟踪:验证日期、事件、用户名/ID、旧值、新值等。在审计跟踪中被正确捕获。
126.  审计线索:尝试修改审计线索。
127.  审计线索:尝试删除审计线索。
128.  审计线索:导出审计线索。
129.  **安全性:**检查权限模型。
130.  安全性:尝试访问不允许访问的内容。
131.  安全性:检查您是否可以看到应该为您隐藏的字段
132.  安全性:尝试编辑不允许编辑的内容。
133.  安全性:尝试启动不允许您启动的工作流。
134.  安全性:验证只有可用的工作流存在。
135.  安全性:谁可以参与工作流？
136.  保安:谁可以签字？
137.  安全性:允许对文档的次要/主要版本做什么？
138.  安全性:尝试将恶意代码注入到应用程序的字段中。
139.  安全性:检查只有管理员帐户/用户可以访问管理控制台，普通用户不能访问它。
140.  安全性:验证不同的组织不会意外地看到/访问彼此的数据。
141.  **性能:**检查不同国家(全球)的延迟。
142.  性能:检查连接中断时会发生什么。
143.  性能:数据应该被缓存吗？
144.  性能:您使用本地数据库吗？检查数据存储是否正确，如果删除一个项目会发生什么，等等？
145.  性能:动态加载旧内容，在后台，滚动时等。？
146.  性能:测试同时登录的用户数量。
147.  性能:执行负载测试。
148.  **备份:**备份测试(完整备份+增量备份)。
149.  备份:从备份恢复的测试。
150.  **离线模式:**内容是否应该可以离线访问？
151.  离线模式:wifi/载波信号恢复时同步。
152.  脱机模式:当多个用户试图在联机/脱机模式下修改同一个项目时，检查同步/合并问题。
153.  **邀请:**输入时验证电子邮件地址。
154.  邀请:在“发送/添加”时验证电子邮件地址，无需按 Enter。
155.  邀请:邀请多人。尽量使用长字符串，不带分隔符、空格、逗号、分号等。
156.  邀请函:不正确的电子邮件地址(没有@，拼写错误如@gamil.com 而不是 gamil.com 等)。
157.  邀请:验证邀请电子邮件是否已发送和接收。
158.  邀请:你能从你的电子邮件、设备或应用程序中的好友列表中获取联系信息吗？
159.  **推荐计划:**推荐计划有效吗？比如，当用户邀请的人注册时，他们会得到预期的积分吗(ala Dropbox 和优步)？
160.  **Premium:** 支付模块能用吗？
161.  高级:用户升级后可以使用高级功能吗？
162.  高级:降级帐户并检查对高级功能的访问是否已被删除(立即或在订购期到期时)。
163.  **重新排序:**重新排序项目，并验证所有平台的排序是否正确。
164.  重新排序:列出一个超过 10 项的清单。对 1–10 和+10 范围内的项目重新排序，并检查排序是否正确保存。
165.  **收藏:**标记/星星/收藏/钉一个物品。验证重新排序项目或应用排序时项目不受影响。
166.  **排序:**检查排序(字母、截止日期、类别、创建日期、标签等。).
167.  排序:支票排序不区分大小写。
168.  排序:检查日期排序使用不同的年，月，日。
169.  排序:检查数字排序。经典的 1，10，11，12… 2，21，22。
170.  排序:让两个不同的用户使用不同的排序打开应用程序。让一个用户编辑一个项目。验证在第二个用户的屏幕上更新了正确的项目。
171.  **过滤器:**检查过滤器是否按预期工作。可以同时应用多个过滤器吗？
172.  过滤器:假设您想过滤一个首字母为“NJ”的特定用户，而另一个用户的首字母为“NJI”。过滤器是否只显示与“NJ”完全匹配的项目？还是也包括“NJI”的结果？
173.  **搜索:**开始打字时是否提供建议？
174.  搜索:是否返回预期结果？
175.  搜索:你是否只看到你被允许看到的内容/结果？
176.  **视图:**检查不同的视图，确保数据显示正确。例如列表视图、平铺视图、缩略图视图、表格视图等。
177.  视图:打开/关闭项目(像在日历中一样),并验证视图中显示的数据是否正确。
178.  视图:展开/折叠视图，隐藏/显示列等。
179.  **报告&仪表板**:验证仪表板上显示的数据是否正确。
180.  报告和仪表板:验证数据是否被正确提取到报告中。
181.  **设置:**更改团队设置。验证它是否适用于组中的所有用户。
182.  设置:更改单个设置。验证它不会影响组中的任何其他用户。
183.  设置:更改时区，并验证时间戳是否正确反映了所有用户。
184.  设置:您的应用程序中的语言是否应该根据浏览器中检测到的默认语言来显示？可以手动更改吗？
185.  **通知:**查看相关通知是否出现在您的通知中心。
186.  通知:你能清除通知吗？
187.  通知:一个项目被查看后，通知是否被清除？
188.  通知:关闭电子邮件通知，并确认它们没有被发送。
189.  通知:检查退订邮件是否按预期工作。
190.  通知:验证警报/提醒是否在预定时间开启/关闭。
191.  通知:人们在提到他们的时候会被通知吗？如果他们禁用了通知，会发生什么？
192.  通知:当用户点击电子邮件通知中的链接时，它应该在哪里打开？应该重定向到移动应用程序还是 web 应用程序？
193.  **快捷键:**复制/粘贴。
194.  快捷键:在字段之间使用制表符。
195.  快捷键:使用其他键盘快捷键。
196.  **工具:**检查导入工具。
197.  工具:检查导出工具，包括打印。
198.  工具:检查迁移工具(导出然后导入)。
199.  浏览器:检查 Chrome、Firefox、Safari、Internet Explorer、Edge 等浏览器的功能。
200.  浏览器:检查与以前浏览器版本的兼容性。
201.  浏览器:检查滚动(垂直+水平)。
202.  浏览器:检查在调整浏览器大小时内容是否仍然正确显示。使用[browsersize.com](https://browsersize.com/)等工具检查浏览器尺寸，查看其在分辨率为 1366 x 768 像素的 MacBook 上的显示效果。
203.  浏览器:如果你使用 hellobar(例如来自[Hellobar.com](https://www.hellobar.com/))检查它是否影响你的应用程序的 UI。
204.  **移动:**根据用户选择的屏幕更新导航栏中的内容。
205.  移动:点击一个字段时出现键盘。
206.  移动:滚动或点击屏幕上的其他位置时，键盘会消失。
207.  移动:检查滑动手势。
208.  移动:快速点击屏幕上的任何地方(也可以是字段之外，靠近屏幕边界等。).
209.  **推送通知:**有没有在杀死状态下收到推送通知？
210.  推送通知:当应用程序在后台运行时，你会收到推送通知吗？
211.  推送通知:当应用程序在前台时，你会收到推送通知吗？
212.  推送通知:当应用程序从离线模式返回到在线模式时，你会收到推送通知吗？
213.  推送通知:关闭推送通知，并确认您没有收到推送通知。将其重新打开，并验证是否收到推送通知。
214.  **iPhone:** 测试向后兼容 iOS12、iOS11、iOS10…例如 iPhone5 只支持 iOS9。
215.  iPhone:清除徽章计数。什么时候？
216.  iPhone:在通知中心显示推送通知，何时清除？
217.  **安卓:**向后兼容(奥利奥、牛轧糖、棉花糖等。).
218.  Android:推送通知分组正确吗(如果你分组推送通知的话)？
219.  **桌面应用:**检查 Window 桌面应用的功能。
220.  桌面应用程序:检查 Mac 应用程序的功能。
221.  **集成:**外部应用可以添加到你的应用中吗？
222.  集成:与其他应用程序的集成是否如预期的那样工作？数据导出、导入和同步是否正确？
223.  集成:你测试过你的 API 吗？
224.  机器人:你的机器人提供相关信息和正确答案吗？
225.  升级:升级你的数据模型。检查以前版本的用户是否有任何问题。如果出现问题，检查自动升级到最新稳定版本的机制是否正常工作。
226.  升级:如果您交付内部解决方案(如 SharePoint)，测试从一个版本到另一个版本的不同升级路径(从精确版本直接升级到最新版本，跳过次要的中间版本等)。).
227.  **删除账户:**最后，确认你可以删除你的账户。

# 速度与质量

如果你经常发布，而且你的应用功能丰富，你可能需要一个或多个全职的 QA 工程师来确保你持续提供高质量的应用。

***动作快，破事。这是脸书最初的座右铭。对于没有太多牵引力的早期创业公司来说，这可能是一个不错的方法，但随着你的成熟，你(和你的客户)需要稳定性。***

这就是为什么脸书把他们的座右铭改成了 ***用稳定的基础设施快速行动*** 因为修复 bug 会减缓开发。

![](img/c5ecb0b31917e0bb583e57cd3711735e.png)

Facebook’s original and new motto.

# 如何帮助你的工程师？

如果你说“它不工作”而不提供任何细节，没有什么比这更让你的开发人员沮丧的了。

提供以下信息，让您的开发人员高兴。这当然也会加快修复观察到的问题的时间😉

1.  记录问题发生的时间。
2.  请确保您能够始终如一地重现该问题。
3.  描述您遵循的具体步骤。
4.  打开浏览器并按 F12。然后重现该问题。打开控制台和网络选项卡，并将结果提供给开发人员。*注意:在重现问题之前，最好清除控制台和网络中的数据。*

# 手动还是自动测试？

如果你构建一个跨平台的解决方案，你将会有大量的测试组合。所以你需要明智地开发你的测试策略。做适量的测试——不要太少——但也不要测试所有的组合。

如果你从事 QA 工作，但是没有任何编码经验，那么与工程师交流可能是值得的，因为一些你认为重要的测试内容可能是不相关的。

您可以设置自动化测试工具——或者执行手动测试。最佳选择取决于产品的成熟度和公司的规模。

自动化测试工具听起来很棒，但是你需要一个真正成熟的产品才有意义。你需要知道核心功能、用户界面和 UX 在很长一段时间内都不会改变。否则，您必须不断地更新测试脚本。

自动化测试工具也不能发现不正确的东西。它可以是更软的东西，如用户界面，拼写，对齐等。这对用户体验很重要。

# 最后的话

我们基于本文列出的大量原则和测试构建了 [SquidHub](http://www.squidhub.com) (一个团队协作应用程序)。

我们很想听听你的最佳建议。请在下面评论，我们将更新这篇文章(为了所有应用程序开发人员、产品经理、测试工程师等的利益)。

## 如果你喜欢读这篇文章或者觉得它有帮助，请鼓掌👏并与您的网络共享。这对我们来说意义重大。谢了。

[Andreas Overbeck](http://@AndreasOverbeck) 从事 IT 项目管理和质量测试工作超过 10 年，最初曾在 SharePoint 工作过。

他是 [SquidHub](http://www.squidhub.com) 的创始人兼 CEO 一个团队协作应用程序，旨在使团队更快地移动和高效地协作。无需切换应用程序(或标签)，您就可以访问团队的任务、文件和消息。

SquidHub explained in 1 min 39 sec.

> 感谢您的阅读，祝您工作愉快！