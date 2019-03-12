# 超链接 {#超链接}

## 定义 {#定义}

超链接使文档链接到任何其他文档（或其他资源），也可以链接到文档的指定部分，可以在一个简单的网址上提供应用程序（与必须先安装的本地应用程序或其他东西相比）。几乎任何网络内容都可以转换为链接，点击（或激活）超链接将使网络浏览器转到另一个网址（URL）。

URL可以指向HTML文件、文本文件、图像、文本文档、视频和音频文件以及可以在网络上保存的任何其他内容。 如果浏览器不知道如何显示或处理文件，它会询问您是否要打开文件（需要选择合适的本地应用来打开或处理文件）或下载文件（以后处理它）。

## 链接的解析 {#链接的解析}

通过将文本（或其他内容\)转换为&lt;a&gt;元素内的链接来创建基本链接， 给它一个href属性（也称为目标），它将包含您希望链接指向的网址。

`<p>I'm creating a link to`

`<a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.`

`</p>`

### 使用title属性添加支持信息 {#使用title属性添加支持信息}

可能要添加到您的链接的另一个属性是标题；这旨在包含关于链接的补充有用信息，例如页面包含什么样的信息或需要注意的事情。

`<p>I'm creating a link to`

`<a href="https://www.mozilla.org/en-US/"`

`title="The best place to find more information about Mozilla's`

`mission and how to contribute">the Mozilla homepage</a>.`

`</p>`

当链接悬停在其上时，标题将作为工具提示出现。

连接的标题仅当鼠标悬停在其上时才会显示，这意味着使用键盘来导航网页的人很难获取到标题信息。如果标题信息对于页面非常重要，你应该使用所有用户能都方便获取的方式来呈现，例如放在常规文本中。

### 块级链接 {#块级链接}

可以将一些内容转换为链接，甚至是块级元素。如果想要将一个图像转换为链接，只需把图像放到&lt;a&gt;&lt;/a&gt;标签中间。

`<a href="https://www.mozilla.org/en-US/">`

`<img src="mozilla-image.png" alt="mozilla logo that links to the mozilla homepage">`

`</a>`

## 统一资源定位器\(URL\)与路径\(path\)快速入门 {#统一资源定位器(URL)与路径(path)快速入门}

统一资源定位器（英文：Uniform Resource Locator，简写：URL）是一个定义在网络上的位置的一个文本字符串。

URL使用路径查找文件。路径指定文件系统中感兴趣的文件所在的位置。

此目录结构的根目录称为creation-hyperlinks。当在网站上工作时， 你会有一个包含整个网站的目录。在根目录，我们有一个index.html和一个contacts.html文件。在真实的网站上，index.html 将会成为我们的主页或登录页面。

根目录还有两个目录—— pdfs 和projects，它们分别包含一个 PDF \(project-brief.pdf\) 文件和一个index.html 文件。请注意你可以有两个index.html文件，前提是他们在不同的目录下，许多网站就是如此。第二个index.html或许是项目相关信息的主登录界面。

**指向相同目录：**如果index.html（顶层的index.html）想要包含一个超链接指向contacts.html，你只需要指定想要链接的文件名，因为它与当前文件是在同一个目录的. 所以你应该使用的URL是contacts.html:

`<p>Want to contact a specific staff member?`

`Find details on our <a href="contacts.html">contacts page</a>.</p>`

**指向子目录：**如果你想要包含一个超链接到index.html （顶层index.html）指向 projects/index.html，您需要进入项目目录，然后指明要链接到的文件。 通过指定目录的名称，然后是正斜杠，然后是文件的名称。因此您要使用的URL是projects / index.html：

`<p>Visit my <a href="projects/index.html">project homepage</a>.</p>`

**指向上级目录：**如果你想在projects/index.html中包含一个指向pdfs/project-brief.pdf的超链接，你必须返回上级目录，然后再回到pdf目录。“返回上一个目录级”使用两个英文点号表示 — .. — 所以你应该使用的URL是 ../pdfs/project-brief.pdf：

`<p>A link to my <a href="../pdfs/project-brief.pdf">project brief</a>.</p>`

如果需要的话，可以将这些功能的多个例子和复杂的url结合起来。例如：

`../../../complex/path/to/my/file.html`

### 文档片段 {#文档片段}

超链接可以链接到html文档的特定部分（被称为**文档片段**），而不仅仅是文件的顶部。要做到这一点你必须首先分配一个id属性的元素到链接。通常链接到一个特定的标题是有意义的

`<h2 id="Mailing_address">Mailing address</h2>`

然后链接到那个特定的id，您可以在URL的结尾包含它，前面是一个井号（\#），例如：

`<p>Want to write us a letter? Use our <a href="contacts.html#Mailing_address">mailing address</a>.</p>`

你甚至可以用它自己的文档片段参考链接到同一份文件的另一部分：

`<p>The <a href="#Mailing_address">company mailing address</a> can be found at the bottom of this page.</p>`

### 绝对链接和相对链接

**绝对URL**： 指向由其在Web上的绝对位置定义的位置，包括 协议 and 域名. 像下面的例子,如果index.html 页面上传到projects这一个目录 。project位于web服务站点的根目录, web站点的域名为[http://www.example.com](http://www.example.com/), 这个页面可以通过[http://www.example.com/projects/index.html访问](http://www.example.com/projects/index.html%E8%AE%BF%E9%97%AE)\( 或者仅仅通过[http://www.example.com/projects/来访问](http://www.example.com/projects/%E6%9D%A5%E8%AE%BF%E9%97%AE), 因为大多数web服务通过访问index.html这样的页面来加载，如果没有特定的URL的话\)

**绝对URL总是指向相同的位置，不管它在哪里使用。**

**相对URL**： 指向与您链接的文件相关的位置。例如，如果我们想从示例文件链接[http://www.example.com/projects/index.html转到相同目录下的一个PDF文件](http://www.example.com/projects/index.html%E8%BD%AC%E5%88%B0%E7%9B%B8%E5%90%8C%E7%9B%AE%E5%BD%95%E4%B8%8B%E7%9A%84%E4%B8%80%E4%B8%AAPDF%E6%96%87%E4%BB%B6), URL就是文件名URL — 例如 project-brief.pdf —没有其他的信息要求. 如果PDF文件能够在projects的子目录pdfs中访问到, 相对路径就是pdfs/project-brief.pdf \(对应的绝对URL就是[http://www.example.com/projects/pdfs/project-brief.pdf.\](http://www.example.com/projects/pdfs/project-brief.pdf./)\)

一个相对URL将指向不同的位置，这取决于它所在的文件所在的位置——例如，如果我们把index.html 文件 从 projects 目录移动出来并进入Web站点的根目录（最高级别，而不是任何目录中）， pdfs/project-brief.pdf 的相对URL将会指向[http://www.example.com/pdfs/project-brief.pdf](http://www.example.com/pdfs/project-brief.pdf), 而不是[http://www.example.com/projects/pdfs/project-brief.pdf](http://www.example.com/projects/pdfs/project-brief.pdf).

## 链接最佳实践 {#链接最佳实践}

### 用清晰的链接措辞 {#用清晰的链接措辞}

把链接放在你的页面上很容易。这还不够。我们需要让所有的读者都可以使用链接，不管他们当前的环境和哪些工具。

使用屏幕阅读器的用户喜欢从页面上的一个链接跳到另一个链接，并且脱离上下文来阅读链接。

搜索引擎使用链接文本为索引目标文件所以，在链接文本中包含关键词是一个很好的主意，以有效地描述与之相关的信息。

读者往往会浏览页面而不是阅读每一个字，他们的眼睛会被页面的特征所吸引，比如链接。他们会找到描述性的链接。

好链接文本：Download Firefox

`<p><a href="https://firefox.com/">`

`  Download Firefox`

`</a></p>`

坏链接文本：Click here to download Firefox

`<p><a href="https://firefox.com/">`

`  Click here`

`</a>`

`to download Firefox</p>`

不要重复URL作为链接文本的一部分 — URL看起来很丑，当屏幕朗读器一个字母一个字母的读出来的时候听起来就更丑了。

不要在链接文本中说“link”或“links to”——它只是噪音。屏幕阅读器告诉人们有一个链接。可视化用户也会知道有一个链接，因为链接通常是用不同的颜色设计的，并且存在下划线（这个惯例一般不应该被打破，因为用户习惯了它。）

保持你的链接标签尽可能短-长链接尤其惹恼屏幕阅读器用户，他们必须听到整件事读出来。

### 尽可能使用相对链接 {#尽可能使用相对链接}

从上面的描述中，您可能认为始终使用绝对链接是一个好主意；毕竟，当页面像相对链接那样移动时，它们不会中断。但是，**当链接到同一网站的其他位置时，你应该使用相对链接（当链接到另一个网站时，你需要使用绝对链接）**：

首先，检查代码要容易得多——相对URL通常比绝对URL短得多，这使得阅读代码更容易。

其次，在可能的情况下使用相对URL更有效。当使用绝对URL时，浏览器首先通过DNS（见万维网是如何工作的）查找服务器的真实位置，然后再转到该服务器并查找所请求的文件。另一方面，相对URL，浏览器只在同一服务器上查找被请求的文件。因此，如果你使用相对URL做的绝对URL，你就不断地让你的浏览器做额外的工作，这意味着它的效率会降低。

### 链接到非html资源 ——留下清晰的指示 {#链接到非html资源_——留下清晰的指示}

当链接到一个需要下载的资源（如PDF或Word文档）或流媒体（如视频或音频）或有另一个潜在的意想不到的效果（打开一个弹出窗口，或加载Flash电影），你应该添加明确的措辞，以减少任何混乱。如下的例子会让人反感：

如果你是在低带宽连接，点击一个链接，然后就开始下载大文件。

如果你没有安装Flash播放器，点击一个链接，然后突然被带到一个需要Flash的页面。

`<p><a href="http://www.example.com/large-report.pdf">`

`  Download the sales report (PDF, 10MB)`

`</a></p>`

`<p><a href="http://www.example.com/video-stream/">`

`  Watch the video (stream opens in separate tab, HD quality)`

`</a></p>`

`<p><a href="http://www.example.com/car-game">`

`  Play the car game (requires Flash)`

`</a></p>`

### 在下载链接时使用下载属性 {#在下载链接时使用下载属性}

当您链接到要下载的资源而不是在浏览器中打开时，您可以使用下载属性来提供一个默认的保存文件名。

`<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=en-US"`

`   download="firefox-latest-64bit-installer.exe">`

`  Download Latest Firefox for Windows (64-bit) (English, US)`

`</a>`

### 创建一个导航菜单

希望你把一些页面和导航菜单链接起来，创建一个多页面的网站。这是创建网站的一种常见方式——每一页都使用相同的页面结构，包括相同的导航菜单，所以当链接被点击时，它给人的印象是你停留在同一个地方，不同的内容正在被提出来。

在一个页面上的指定位置添加一个无序列表，其中包含要链接到的页面的名称。导航菜单通常只是一个链接列表，因此这在语义上是确定的。

将每个页面名称转换为该页的链接。

将导航菜单复制到每个页面。

在每一页上，只删除同一页的链接——一个页面包含自己的链接是令人困惑和毫无意义的，而缺少链接会对你当前的页面起到很好的视觉提示作用。

## 电子邮件链接 {#电子邮件链接}

当点击一个链接或按钮时，打开一个新的电子邮件发送信息而不是连接到一个资源或页面，这种情况是可能做到的。这样做是使用&lt;a&gt;元素和mailto：URL的方案。

其最基本和最常用的使用形式为一个mailto:link （链接），链接简单说明收件人的电子邮件地址。

`<a href="mailto:nowhere@mozilla.org">Send email to nowhere</a>`

实际上，邮件地址甚至是可选的。如果你忘记了（也就是说，你的href仅仅只是简单的"mailto:"），一个新的发送电子邮件的窗口也会被用户的邮件客户端打开，只是没有收件人的地址信息，这通常在“分享”链接是很有用的，用户可以发送给他们选择的地址邮件

### 具体细节 {#具体细节}

除了电子邮件地址，您还可以提供其他信息。事实上，任何标准的**邮件头字段**可以被添加到你提供的邮件URL。 其中最常用的是主题\(subject\)、抄送\(cc\)和主体\(body\) \(这不是一个真正的头字段，但允许您为新邮件指定一个短内容消息\)。 每个字段及其值被指定为查询项。

`<a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&amp;subject=The%20subject%20of%20the%20email &amp;body=The%20body%20of%20the%20email">`

`  Send mail with cc, bcc, subject and body`

`</a>`

注意：**每个字段的值必须是URL编码的**。 也就是说，**不能有非打印字符**（不可见字符比如制表符、换行符、分页符）和空格 percent-escaped. 同时**注意使用问号（?）来分隔主URL与参数值，以及使用&符来分隔mailto:中的各个参数。** 这是标准的URL查询标记方法。





