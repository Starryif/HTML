# 高阶文字排版

## 描述列表 {#描述列表}

描述列表 \(description list\) 。这种列表的目的是标记一组项目及其相关描述，例如术语和定义，或者是问题和答案等。

描述列表使用与其他列表类型不同的闭合标签— &lt;dl&gt;; 此外，每一项描述术语都用 &lt;dt&gt; \(description term\) 元素闭合。每个描述都用 &lt;dd&gt; \(description description\) 元素闭合。

`<dl>`

`  <dt>内心独白</dt>`

`    <dd>戏剧中，某个角色对自己的内心活动或感受进行念白表演，这些台词只面向观众，而其他角色不会听到。</dd>`

`  <dt>语言独白</dt>`

`    <dd>戏剧中，某个角色把自己的想法直接进行念白表演，观众和其他角色都可以听到。</dd>`

`  <dt>旁白</dt>`

`    <dd>戏剧中，为渲染幽默或戏剧性效果而进行的场景之外的补充注释念白，只面向观众，内容一般都是角色的感受、想法、以及一些背景信息等。</dd>`

`</dl>`

浏览器的默认样式会在描述列表的**描述部分（description description）**和**描述术语（description terms）**之间产生缩进。

请注意：一个术语 &lt;dt&gt; 可以同时有多个描述 &lt;dd&gt;

## 引用 {#引用}

HTML也有用于标记引用的特性，至于使用哪个元素标记，取决于你引用的是一块还是一行。

### 块引用 {#块引用}

如果一个块级内容（一个段落、多个段落、一个列表等）从其他地方被引用，应该把它用&lt;blockquote&gt;元素包裹起来表示，并且在cite属性里用URL来指向引用的资源。

`<blockquote cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote">`

`  <p>The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or <em>HTML Block`

`  Quotation Element</em>) indicates that the enclosed text is an extended quotation.</p>`

`</blockquote>`

浏览器在渲染块引用时默认会增加缩进，作为引用的一个指示符。

### 行内引用 {#行内引用}

行内元素用同样的方式工作，除了使用&lt;q&gt;元素。

`<p>The quote element — <code>&lt;q&gt;</code> — is <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">intended`

`for short quotations that don't require paragraph breaks.</q></p>`

浏览器默认将其作为普通文本放入引号内表示引用。

### 引文 {#引文}

cite属性的内容听起来很有用，但不幸的是，浏览器、屏幕阅读器等等不会真的关心它，如果不使用JavaScript或CSS，浏览器不会显示cite的内容。如果你想要确保引用的来源在页面上是可用的，更好的方法是把&lt;cite&gt;元素放到引用元素旁边。这就意味着包含引用来源的名称——即引用的书的名字，或人的名字——但并不表示你不可以用同样的方式把要链接的文本放到&lt;cite&gt;元素中。

引文默认的字体样式为斜体。

`<p>The quote element — <code>&lt;q&gt;</code> — is <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">intended`

`for short quotations that don't require paragraph breaks.</q> -- <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">`

`<cite>MDN q page</cite></a>.</p>`

## 缩略语 {#缩略语}

**&lt;abbr&gt;**——它常被用来包裹一个缩略语或缩写，并且提供缩写的解释（包含在title属性中）

`<p>第 33 届 <abbr title="夏季奥林匹克运动会">奥运会</abbr> 将于 2024 年 8 月在法国巴黎举行。</p>`

当光标移动到项目上时会出现提示。

还有另一个元素&lt;acronym&gt;，它基本上与&lt;abbr&gt;相同，专门用于首字母缩略词而不是缩略语。 然而，这已经被废弃了 - 它在浏览器的支持中不如&lt;abbr&gt;，并且具有类似的功能，所以没有意义。 只需使用&lt;abbr&gt;。

## 标记联系方式 {#标记联系方式}

HTML有个用于标记联系方式的元素——**&lt;address&gt;**。它仅仅包含你的联系方式

`<address>`

`  <p>Chris Mills, Manchester, The Grim North, UK</p>`

`</address>`

要记住的一点是，&lt;address&gt;元素是为了标记编写HTML文档的人的联系方式，而不是任何其他的内容。因此，如果这是Chris写的文档，上面的内容将会很好。

`<address>`

`  <p>Page written by <a href="../authors/chris-mills/">Chris Mills</a>.</p>`

`</address>`

## 上标和下标 {#上标和下标}

当你使用日期、化学方程式、和数学方程式时会偶尔使用上标和下标。 &lt;sup&gt; 和&lt;sub&gt;元素可以解决这样的问题。

`<p>咖啡因的化学方程式是 C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>。</p>`

`<p>如果 x<sup>2</sup> 的值为 9，那么 x 的值必为 3 或 -3。</p>`

## 展示计算机代码 {#展示计算机代码}

有大量的HTML元素可以来标记计算机代码

&lt;code&gt;: 用于标记计算机通用代码。

&lt;pre&gt;: 对保留的空格（通常是代码块）——如果您在文本中使用缩进或多余的空白，浏览器将忽略它，您将不会在呈现的页面上看到它。但是，如果您将文本包含在&lt;pre&gt;&lt;/pre&gt;标签中，那么空白将会以与你在文本编辑器中看到的相同的方式渲染出来。

&lt;var&gt;: 用于标记具体变量名。

&lt;kbd&gt;: 用于标记输入电脑的键盘（或其他类型）输入。

&lt;samp&gt;: 用于标记计算机程序的输出。

`<pre><code>const para = document.querySelector('p');`

`para.onclick = function() {`

`  alert('噢，噢，噢，别点我了。');`

`}</code></pre>`

`<p>请不要使用 <code>&lt;font&gt;</code> 、 <code>&lt;center&gt;</code> 等表象元素。</p>`

`<p>在上述的 JavaScript 示例中，<var>para</var> 表示一个段落元素。</p>`

`<p>按 <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>A</kbd> 选择全部内容。</p>`

`<pre>$ <kbd>ping mozilla.org</kbd>`

`<samp>PING mozilla.org (63.245.215.20): 56 data bytes`

`64 bytes from 63.245.215.20: icmp_seq=0 ttl=40 time=158.233 ms</samp></pre>`

## 标记时间和日期 {#标记时间和日期}

HTML 还支持将时间和日期标记为可供机器识别的格式的 &lt;time&gt; 元素

`<time datetime="2016-01-20">2016年1月20日</time>`

因为世界上有许多种书写日期的格式，但是这些不同的格式不容易被电脑识别 — 假如你想自动抓取页面上所有事件的日期并将它们插入到日历中， &lt;time&gt; 元素允许你附上清晰的、可被机器识别的 时间/日期来实现这种需求。

`<!-- 标准简单日期 -->`

`<time datetime="2016-01-20">20 January 2016</time>`

`<!-- 只包含年份和月份-->`

`<time datetime="2016-01">January 2016</time>`

`<!-- 只包含月份和日期 -->`

`<time datetime="01-20">20 January</time>`

`<!-- 只包含时间，小时和分钟数 -->`

`<time datetime="19:30">19:30</time>`

`<!-- 还可包含秒和毫秒 -->`

`<time datetime="19:30:01.856">19:30:01.856</time>`

`<!-- 日期和时间 -->`

`<time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>`

`<!-- 含有市区偏移值的日期时间 -->`

`<time datetime="2016-01-20T19:30+01:00">7.30pm, 20 January 2016 is 8.30pm in France</time>`

`<!-- 调用特定的周 -->`

`<time datetime="2016-W04">The fourth week of 2016</time>`









