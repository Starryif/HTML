# 元数据

`<!DOCTYPE html>`

`<html>`

`<head>`

`<meta charset="utf-8">`

`<title>我的测试站点</title>`

`</head>`

`<body>`

`<p>这是我的页面</p>`

`</body>`

`</html>`

元数据就是描述数据的数据。

head 标签是 &lt;head&gt; 元素的内容。不像 &lt;body&gt; 元素的内容可以显示在浏览器中，head 的内容不会在浏览器中显示，它的作用是包含一些页面的元数据。

# `<title>`元素 增加一个标题

`<title>`元素是用来表示整个HTML文档大致内容的元数据（不是文档的内容）。

当被加载到浏览器中的时候，元素 &lt;h1&gt;  会出现在页面中 —— 通常它应该在一个页面中只被使用一次，它被用来标记你的页面内容的标题（故事的标题，新闻标题或者任何适当的方式）。

`<title>`元素的内容被作为浏览器添加书签时，建议的书签名。

`<title>`元素的内容也被用在搜索的结果中。

# &lt;meta&gt;元素

HTML中有一个“官方的”方式来为一个文档添加元数据—— [`<meta>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta)元素。

### 指定文档中字符的编码

`<meta charset="utf-8">`

### 添加作者和描述

`<meta name="author" content="Chris Mills">`

`<meta name="description" content="The MDN Learning Area......">`

name 指定了meta 元素的类型； 说明该元素包含了什么类型的信息。

content 指定了实际的元数据内容。

指定作者在某些情况下是很有用的：如果你需要联系页面的作者，问一些关于页面内容的问题。 一些内容管理系统能够自动获取页面作者的信息，然后用于某种目的。

指定包含关于页面内容的关键字的页面内容的描述是很有用的，因为它可能或让你的页面在搜索引擎的相关的搜索出现得更多 （这些行为术语上被称为 Search Engine Optimization, or SEO.）

在谷歌搜索里，在主页面链接下面，你将看到一些相关子页面 — 这些是站点链接,可以在 Google's webmaster tools 配置— 一种可以使你的站点对搜索引擎更友好的方式。

许多 &lt;meta&gt; 特性已经不再使用。 例如，keyword &lt;meta&gt; 元素（&lt;meta  name="keywords" content="fill, in, your, keywords, here"&gt;）— 提供关键词给搜索引擎，根据不同的搜索词，查找到相关的网站 — 被搜索引擎忽略了， 因为作弊者填充了大量关键词到keyword， 错误地引导搜索结果。

### 其他类型的 metadata

当你在网站上查看源码时，你也会发现其他类型的元数据。你在网站上看到的许多功能都是专有创作，旨在向某些网站\(如社交网站\)提供可使用的特定信息。

Facebook 编写的元数据协议 [Open Graph Data](http://ogp.me/)为网站提供了更丰富的元数据。在 MDN 源代码中，你会发现：

`<meta property="og:image" content="https://developer.cdn.mozilla.net/static/img/opengraph-logo.dc4e08e2f6af.png">`

`<meta property="og:description" content="The Mozilla Developer Network (MDN) provides`

`information about Open Web technologies including HTML, CSS, and APIs for both Web sites`

`and HTML5 Apps. It also documents Mozilla products, like Firefox OS.">`

`<meta property="og:title" content="Mozilla Developer Network">`

上面代码展现的一个效果就是，当你在 Facebook 上链接到 MDN 时，该链接将显示一个图像和描述：这为用户提供更丰富的体验。

Twitter 还拥有自己的类型的**专有元数据协议**，当网站的 URL 显示在 twitter.com 上时，它具有相似的效果。

`<meta name="twitter:title" content="Mozilla Developer Network">`

# 在你的站点增加自定义图标

16 x 16 像素是这种图标的第一种类型。图标出现在浏览器每一个打开的页面中的标签页中中以及在书签面板中的书签页面中。

页面添加图标的方式有：

1.将其保存在与网站的索引页面相同的目录中，以.ico格式保存（大多数浏览器将支持更通用的格式，如.gif或.png，但使用ICO格式将确保它能在如Internet Explorer 6一样久远的浏览器显示）

2.将以下行添加到HTML &lt;head&gt;中以引用它：

`<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">`

# 在HTML中应用CSS和JavaScript

`<link>`元素经常位于文档的头部。这个link元素有2个属性，rel="stylesheet"表明这是文档的样式表，而 href包含了样式表文件的路径：

`<link rel="stylesheet" href="my-css-file.css">`

`<script>`部分没必要非要放在文档头部；实际上，把它放在文档的尾部（在 &lt;/body&gt;标签之前）是一个更好的选择，这样可以确保在加载脚本之前浏览器已经解析了HTML内容（如果脚本加载某个不存在的元素，浏览器会报错）。

`<script src="my-js-file.js"></script>`

`script>`元素看起来像一个空元素，但它并不是，因此需要一个结束标记。还可以选择将脚本放入`<script>`元素中，而不是指向外部脚本文件。

# 为文档设定主语言

通过添加lang属性到HTML开始标签中来实现

`<html lang="en-US">`

如果HTML文档的语言设置好了，那么HTML文档就会被搜索引擎更有效地索引 \(例如，允许它在特定于语言的结果中正确显示\)，对于那些使用屏幕阅读器的视障人士也很有用\(比如， 法语和英语中都有“six”这个单词，但是发音却完全不同\)。

还可以将文档的分段设置为不同的语言

`<p>Japanese example: <span lang="jp">ご飯が熱い。</span>.</p>`



