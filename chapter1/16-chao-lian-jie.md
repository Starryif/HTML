# 超链接

## 定义

超链接使文档链接到任何其他文档（或其他资源），也可以链接到文档的指定部分，可以在一个简单的网址上提供应用程序（与必须先安装的本地应用程序或其他东西相比）。几乎任何网络内容都可以转换为链接，点击（或激活）超链接将使网络浏览器转到另一个网址（URL）。

URL可以指向HTML文件、文本文件、图像、文本文档、视频和音频文件以及可以在网络上保存的任何其他内容。 如果浏览器不知道如何显示或处理文件，它会询问您是否要打开文件（需要选择合适的本地应用来打开或处理文件）或下载文件（以后处理它）。

## 链接的解析 {#链接的解析}

通过将文本（或其他内容\)转换为&lt;a&gt;元素内的链接来创建基本链接， 给它一个href属性（也称为目标），它将包含您希望链接指向的网址。

`<p>I'm creating a link to`

`<a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.`

`</p>`

### 使用title属性添加支持信息

可能要添加到您的链接的另一个属性是标题；这旨在包含关于链接的补充有用信息，例如页面包含什么样的信息或需要注意的事情。

`<p>I'm creating a link to`

`<a href="https://www.mozilla.org/en-US/"`

`   title="The best place to find more information about Mozilla's`

`          mission and how to contribute">the Mozilla homepage</a>.`

`</p>`

当链接悬停在其上时，标题将作为工具提示出现。

连接的标题仅当鼠标悬停在其上时才会显示，这意味着使用键盘来导航网页的人很难获取到标题信息。如果标题信息对于页面非常重要，你应该使用所有用户能都方便获取的方式来呈现，例如放在常规文本中。

### 块级链接 {#块级链接}

可以将一些内容转换为链接，甚至是块级元素。如果想要将一个图像转换为链接，只需把图像放到&lt;a&gt;&lt;/a&gt;标签中间。

`<a href="https://www.mozilla.org/en-US/">`

`  <img src="mozilla-image.png" alt="mozilla logo that links to the mozilla homepage">`

`</a>`

## 统一资源定位器\(URL\)与路径\(path\)快速入门 {#统一资源定位器(URL)与路径(path)快速入门}

统一资源定位器（英文：Uniform Resource Locator，简写：URL）是一个定义在网络上的位置的一个文本字符串。

URL使用路径查找文件。路径指定文件系统中感兴趣的文件所在的位置。

此目录结构的根目录称为creation-hyperlinks。当在网站上工作时， 你会有一个包含整个网站的目录。在根目录，我们有一个index.html和一个contacts.html文件。在真实的网站上，index.html 将会成为我们的主页或登录页面。

根目录还有两个目录—— pdfs 和projects，它们分别包含一个 PDF \(project-brief.pdf\) 文件和一个index.html 文件。请注意你可以有两个index.html文件，前提是他们在不同的目录下，许多网站就是如此。第二个index.html或许是项目相关信息的主登录界面。

**指向相同目录：**如果index.html（顶层的index.html）想要包含一个超链接指向contacts.html，你只需要指定想要链接的文件名，因为它与当前文件是在同一个目录的. 所以你应该使用的URL是contacts.html:

`<p>Want to contact a specific staff member?`

`Find details on our <a href="contacts.html">contacts page</a>.</p>`

**指向子目录：**如果你想要包含一个超链接到index.html （顶层index.html）指向 projects/index.html，您需要进入项目目录，然后指明要链接到的文件。 通过指定目录的名称，然后是正斜杠，然后是文件的名称。因此您要使用的URL是projects / index.html：

`<p>Visit my <a href="projects/index.html">project homepage</a>.</p>`

**指向上级目录：** 如果你想在projects/index.html中包含一个指向pdfs/project-brief.pdf的超链接，你必须返回上级目录，然后再回到pdf目录。“返回上一个目录级”使用两个英文点号表示 — .. — 所以你应该使用的URL是 ../pdfs/project-brief.pdf：

`<p>A link to my <a href="../pdfs/project-brief.pdf">project brief</a>.</p>`

如果需要的话，可以将这些功能的多个例子和复杂的url结合起来。例如：

`../../../complex/path/to/my/file.html`

### 文档片段 {#文档片段}

超链接可以链接到html文档的特定部分（被称为**文档片段**），而不仅仅是文件的顶部。要做到这一点你必须首先分配一个id属性的元素到链接。通常链接到一个特定的标题是有意义的

`<h2 id="Mailing_address">Mailing address</h2>`

然后链接到那个特定的id，您可以在URL的结尾包含它，前面是一个井号（\#），例如：

`<p>Want to write us a letter? Use our <a href="contacts.html#Mailing_address">mailing address</a>.</p>`

你甚至可以用它自己的文档片段参考链接到同一份文件的另一部分：

`<p>The <a href="#Mailing_address">company mailing address</a> can be found at the bottom of this page.</p>`

### 绝对链接和相对链接 {#绝对链接和相对链接}

**绝对URL**： 指向由其在Web上的绝对位置定义的位置，包括 协议 and 域名. 像下面的例子,如果index.html 页面上传到projects这一个目录 。project位于web服务站点的根目录, web站点的域名为http://www.example.com, 这个页面可以通过http://www.example.com/projects/index.html访问 \( 或者仅仅通过http://www.example.com/projects/来访问, 因为大多数web服务通过访问index.html这样的页面来加载，如果没有特定的URL的话\)

**绝对URL总是指向相同的位置，不管它在哪里使用。**

**相对URL**： 指向与您链接的文件相关的位置。例如，如果我们想从示例文件链接http://www.example.com/projects/index.html转到相同目录下的一个PDF文件, URL就是文件名URL — 例如 project-brief.pdf —没有其他的信息要求. 如果PDF文件能够在projects的子目录pdfs中访问到, 相对路径就是pdfs/project-brief.pdf \(对应的绝对URL就是 http://www.example.com/projects/pdfs/project-brief.pdf.\)

一个相对URL将指向不同的位置，这取决于它所在的文件所在的位置——例如，如果我们把index.html 文件 从 projects 目录移动出来并进入Web站点的根目录（最高级别，而不是任何目录中），  pdfs/project-brief.pdf 的相对URL将会指向http://www.example.com/pdfs/project-brief.pdf, 而不是http://www.example.com/projects/pdfs/project-brief.pdf.









