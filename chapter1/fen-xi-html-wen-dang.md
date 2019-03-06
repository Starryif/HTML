# 分析HTML文档

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

1.`<!DOCTYPE html>`: 声明文档类型. 很久以前，早期的HTML\(大约1991年2月\)，文档类型声明类似于链接，规定了HTML页面必须遵从的良好规则，能自动检测错误和其他有用的东西。使用如下：

`<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"`

`"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"`

然而现在没有人再这样写，需要保证每一个东西都正常工作已成为历史。只需要知道

`<!DOCTYPE html>`是最短的有效的文档声明。

2.&lt;html&gt;&lt;/html&gt;: &lt;html&gt;元素。这个元素包裹了整个完整的页面，是一个**根元素**。

3.&lt;head&gt;&lt;/head&gt;: &lt;head&gt;元素. 这个元素是一个容器，它包含了所有想包含在HTML页面中但不想在HTML页面中显示的内容。这些内容包括想在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等。

4.&lt;meta charset="utf-8"&gt;: 这个元素设置文档使用utf-8字符集编码，utf-8字符集包含了人类大部分的文字。基本上能识别放上去的所有文本内容。毫无疑问要使用它，并且它能在以后避免很多其他问题。

5.&lt;title&gt;&lt;/title&gt;: 设置页面标题，出现在浏览器标签上，当标记/收藏页面时它可用来描述页面。

6.&lt;body&gt;&lt;/body&gt;: &lt;body&gt;元素。 包含了访问页面时所有显示在页面上的内容，文本，图片，音频，游戏等等。

