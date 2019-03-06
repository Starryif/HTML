# 定义

HTML由一系列的元素（elements）组成，这些元素可以用来包围不同部分的内容，使其以某种方式呈现或者工作。

> &lt;p&gt;这是一个段落&lt;/p&gt;
>
> 开始标签 内容 结束标签

**开始标签**（Opening tag）：包含元素的名称（本例为 p），被大于号、小于号所包围。表示元素从这里开始或者开始起作用 。

**结束标签**（Closing tag）：与开始标签相似，只是其在元素名之前包含了一个斜杠。这表示着元素的结尾。

**内容**（Content）：元素的内容，所输入的文本本身。

**元素**（Element）：开始标签、结束标签与内容相结合，便是一个完整的元素。

HTML 标签不区分大小写。输入标签时既可以使用大写字母也可以使用小写字母。例如，标签 &lt;title&gt; 写作&lt;title&gt;、&lt;TITLE&gt;、&lt;Title&gt;、&lt;TiTlE&gt;，等等都可以正常工作。不过，从一致性、可读性等各方面来说，**最好仅使用小写字母**。

# 嵌套元素

可以把元素放到其它元素之中，这被称作嵌套。

> &lt;p&gt;这是一个&lt;strong&gt;段落&lt;/strong&gt;&lt;/p&gt;

# 块级元素和内联元素

块级元素在页面中以块block的形式展现，**相对与其前面的内容它会出现在新的一行，其后的内容也会被挤到下一行展现**。块级元素通常用于展示页面上结构化的内容，例如段落、列表、导航菜单、页脚等等。一个以block形式展现的块级元素不会被嵌套进内联元素中，但可以嵌套在其它块级元素中。

内联元素通常出现在块级元素中并包裹文档内容的一小部分，而不是一整个段落或者一组内容。**内联元素不会导致文本换行**：它通常出现在一堆文字之间。

# 空元素Empty elements/Void elements

不是所有元素都拥有开始标签，内容和结束标签。 一些元素只有一个标签，通常用来在此元素所在位置插入/嵌入一些东西。

> &lt;img src="[https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"](https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"]%28https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"]%28https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png>]%28https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"]%28https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"&gt%29&gt%29&gt)&gt;

## 属性 {#属性}

元素也可以拥有属性，属性包含元素的额外信息，这些信息不会出现在实际的内容中。

> &lt;p class="editor-note"&gt;这是一个段落&lt;/p&gt;

这个class属性给元素赋了一个识别的名字（id），这个名字此后可以被用来识别此元素的样式信息和其他信息。

一个属性必须包含如下内容：

1. 在元素名和属性名之间有个空格space \(如果有一个或多个已存在的属性，就与前一个属性之间有一个空格.\)
2. 属性名后面紧跟着一个“=”符号.
3. 有一个属性值,由一对引号“ ”引起来.

# 布尔属性

没有属性值的属性被称为布尔属性，它们只能有跟它的属性名一样的属性值。例如disabled 属性，它们可以标记表单输入使之变为不可用\(变灰色\)，此时用户不能向他们输入任何数据。

> &lt;input type="text" disabled="disabled"&gt;
>
> &lt;input type="text" disabled&gt;

# 省略包围属性值的引号

不给属性值添加引号。在某些情况下它是被允许的，但是其他情况下会破坏标记。**建议始终添加引号**，这样可以避免很多问题，并且使代码更易读。

# 单引号或者双引号

双引号或者单引号，只是风格的问题。

> &lt;a href="[http://www.example.com"&gt;双引号&lt;/a&gt;](http://www.example.com">双引号</a>]%28http://www.example.com">双引号)
>
> &lt;a href='[http://www.example.com'&gt;单引号&lt;/a](http://www.example.com'>单引号</a]%28http://www.example.com'>单引号)&gt;

应该注意单引号和双引号不能在一个属性值里面混用。

> &lt;a href="[http://www.example.com'&gt;错误的语法&lt;/a&gt;](http://www.example.com'>错误的语法</a>]%28http://www.example.com'>错误的语法)

在一个HTML中已使用一种引号，可以在此引号中嵌套另外一种引号：

> &lt;a href="[http://www.example.com](http://www.example.com)" title="这样'行不行'？"&gt;双引号嵌套单引号&lt;/a&gt;

如果想将引号当作文本显示在html中，就必须使用实体引用。

