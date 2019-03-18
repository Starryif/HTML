# 在网页中添加矢量图形

矢量图形在很多情况下非常有用 — 它们拥有较小的文件尺寸，却高度可缩放，所以它们不会在镜头拉近或者放大图像时像素化。

## 什么是矢量图形 {#什么是矢量图形？}

在网上，你会和两种类型的图片打交道 — 位图和矢量图

位图使用**像素网格**来定义 — 一个位图文件精确得包含了每个像素的位置和它的色彩信息。流行的位图格式包括 Bitmap \(.bmp\), PNG \(.png\), JPEG \(.jpg\), and GIF \(.gif.\)

矢量图使用**算法**来定义 — 一个矢量图文件包含了图形和路径的定义，电脑可以根据这些定义计算出当它们在屏幕上渲染时应该呈现的样子。 SVG 格式可以让我们创造用于 Web 的精彩的矢量图形。

当你放大网页的时候，区别就会变得明显起来 — 随着你的放大，PNG 图片变得像素化了，因为它存储是每个像素的颜色和位置信息 — 当它被放大时，每个像素就被放大以填满屏幕上更多的像素，所以图像就会开始变得马赛克感觉。矢量图像看起来仍然效果很好且清晰，因为无论它的尺寸如何，都使用算法来计算出图像的形状，仅仅是根据放大的倍数来调整算法中的值。

矢量图形相较于同样的位图，通常拥有更小的体积，因为它们仅需储存少量的算法，而不是逐个储存每个像素的信息。

## SVG是什么？ {#SVG是什么？}

SVG 是用于描述矢量图像的XML语言。 它基本上是像HTML一样的标记，只是你有许多不同的元素来定义要显示在图像中的形状，以及要应用于这些形状的效果。 SVG用于标记图形，而不是内容。 非常简单，你有一些元素来创建简单图形，如&lt;circle&gt; 和&lt;rect&gt;。更高级的SVG功能包括 &lt;feColorMatrix&gt;（使用变换矩阵转换颜色）&lt;animate&gt; （矢量图形的动画部分）和 &lt;mask&gt;（在图像顶部应用蒙版）

作为一个简单的例子，以下代码创建一个圆和一个矩形：

`<svg version="1.1"`

`     baseProfile="full"`

`     width="300" height="200"`

`     xmlns="http://www.w3.org/2000/svg">`

`  <rect width="100%" height="100%" fill="black" />`

`  <circle cx="150" cy="100" r="90" fill="blue" />`

`</svg>`

从上面的例子可以看出，SVG很容易手工编码。 是的，您可以在文本编辑器中手动编写简单的SVG，但是对于复杂的图像，这很快就开始变得非常困难。 为了创建SVG图像，大多数人使用**矢量图形编辑器**，如 Inkscape 或 Illustrator。 这些软件包允许您使用各种图形工具创建各种插图，并创建照片的近似值（例如Inkscape的跟踪位图功能）。注意：在Inkscape中，将文件保存为纯SVG以节省空间。 

SVG除了迄今为止所描述的以外还有其他优点：

矢量图像中的文本仍然可访问（这也有利于 SEO\)）。

SVG 可以很好地适应样式/脚本，因为图像的每个组件都是可以通过CSS或通过JavaScript编写的样式的元素。

那么为什么会有人想使用**光栅图形**而不是SVG？ 其实 SVG 确实有一些缺点：

SVG非常容易变得复杂，这意味着文件大小会增加; 复杂的SVG也会在浏览器中占用很长的处理时间。

SVG可能比栅格图像更难创建，具体取决于您尝试创建哪种图像。

旧版浏览器不支持SVG，因此如果您需要在网站上支持旧版本的 IE，则可能不适合（SVG从IE9开始得到支持）。

由于上述原因，光栅图形更适合照片那样复杂精密的图像。

## 将SVG添加到页面 {#将SVG添加到页面}

在本节中，我们将介绍将SVG矢量图形添加到网页的不同方式。

### 快捷方式：&lt;img&gt;

要通过 &lt;img&gt;元素嵌入SVG，你只需要按照预期的方式在 src 属性中引用它。你将需要一个height或width属性（或者如果您的SVG没有固有的宽高比）。

优点

快速，熟悉的图像语法与alt属性中提供的内置文本等效。

可以通过在&lt;a&gt;元素嵌套&lt;img&gt;，使图像轻松地成为超链接。

缺点

无法使用JavaScript操作图像。

如果要使用CSS控制SVG内容，则必须在SVG代码中包含内联CSS样式。 （从SVG文件调用的外部样式表不起作用）

不能用CSS伪类来重设图像样式（如:focus）。

### 疑难解答和跨浏览器支持 {#疑难解答和跨浏览器支持}

对于不支持SVG（IE 8及更低版本，Android 2.3及更低版本）的浏览器，您可以从src属性引用PNG或JPG，并使用srcset属性 只有最近的浏览器才能识别）来引用SVG。 在这种情况下，仅支持浏览器将加载SVG - 较旧的浏览器将加载PNG：

`<img src="equilateral.png" alt="triangle with equal sides" srcset="equilateral.svg">`

还可以使用SVG作为CSS背景图像，如下所示。 在下面的代码中，旧版浏览器会坚持他们理解的PNG，而较新的浏览器将加载SVG：

`background: url("fallback.png") no-repeat center;`

`background-image: url("image.svg");`

`background-size: contain;`

像上面描述的&lt;img&gt;方法一样，使用 CSS 背景图像插入SVG 意味着它不能被 JavaScript 操作，并且也受到相同的 CSS 限制。

如果 SVG 根本没有显示，可能是因为你的服务器设置不正确。 

### 如何在HTML中引入SVG代码 {#如何在HTML中引入SVG代码}

你还可以在文本编辑器中打开SVG文件，复制SVG代码，并将其粘贴到HTML文档中 - 这有时称为将**SVG内联或内联SVG**。确保您的SVG代码在&lt;svg&gt;&lt;/svg&gt;标签中（不要在外面添加任何内容）。

`<svg width="300" height="200">`

`    <rect width="100%" height="100%" fill="green" />`

`</svg>`

优点

将 SVG 内联减少 HTTP 请求，可以减少加载时间。

您可以为 SVG 元素分配class和id，并使用 CSS 修改样式，无论是在SVG中，还是 HTML 文档中的 CSS 样式规则。 实际上，您可以使用任何 SVG外观属性 作为CSS属性。

内联SVG是唯一可以让您在SVG图像上使用CSS交互（如:focus）和CSS动画的方法（即使在常规样式表中）。

您可以通过将 SVG 标记包在&lt;a&gt;元素中，使其成为超链接。

缺点

这种方法只适用于在一个地方使用的SVG。多次使用会导致**资源密集型维护（resource-intensive maintenance）**。

额外的 SVG 代码会增加HTML文件的大小。

浏览器不能像缓存普通图片一样缓存内联SVG。

您可能会在&lt;foreignObject&gt; 元素中包含回退，但支持 SVG 的浏览器仍然会下载任何后备图像。你需要考虑仅仅为支持过时的浏览器，而增加额外开销是否真的值得。

### 如何使用 &lt;iframe&gt; 嵌入SVG

您可以在浏览器中打开 SVG 图像，就像网页一样。 因此，使用&lt;iframe&gt;嵌入 SVG 文档就像我们在 从对象到iframe - 其他嵌入技术 中进行研究一样。

`<iframe src="triangle.svg" width="500" height="500" sandbox>`

`    <img src="triangle.png" alt="Triangle with three unequal sides" />`

`</iframe>`

缺点

如你所知， iframe有一个回退机制，如果浏览器不支持iframe，则只会显示回退。

此外，除非 SVG 和您当前的网页具有相同的 origin，否则你不能在主页面上使用 JavaScript 来操纵 SVG。







