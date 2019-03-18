# 视频和音频内容

## web 中的音频和视频 {#web_中的音频和视频}

web 开发者们一直以来想在 Web 中使用音频和视频，自21世纪初以来，我们的带宽开始能够支持任意类型的视频（视频文件比文本和图片要大的多）。在早些时候，传统的 web 技术（如 HTML ）不能够在 Web 中嵌入音频和视频，所以一些像 Flash \(后来有 Silverlight \) 的专利技术在处理这些内容上变得很受欢迎。这些技术能够正常的工作，但是却有着一系列的问题，包括无法很好的支持 HTML/CSS 特性、安全问题，以及可行性问题。

传统的解决方案能够解决许多这样的问题，前提是它能够正确的工作。幸运的是，几年之后 HTML5 标准提出，其中有许多的新特性，包括 &lt;video&gt; 和 &lt;audio&gt; 标签，以及一些 JavaScript 和 APIs 用于对其进行控制。

在你开始之前，你应当了解一些 OVPs \(在线视频提供商\) 例如 YouTube 、Dailymotion 、 Vimeo, 以及在线音频提供商例如 Soundcloud。这些公司提供方便、简单的方式来支持视频，所以你不必担心庞大的带宽消耗。OVPS 甚至提供现成的代码用于为你的 web 网页嵌入视频/音频。

### &lt;video&gt; 标签 {#<video>_标签}

&lt;video&gt; 允许你简单的嵌入一段视频。

`<video src="rabbit320.webm" controls>

`  <p>你的浏览器不支持 HTML5 视频。可点击<a href="rabbit320.mp4">此链接</a>观看</p>

`</video>`

当中的一些属性如下:

**

同 &lt;img&gt; 标签使用方式相同，src 属性指向你想要嵌入网页当中的视频资源，他们的使用方式完全相同。

**controls

用户必须能够控制视频和音频的回放功能。你可以使用浏览器提供的控制接口，同时你也可以在 JavaScript （JavaScript API）当中使用这些控制接口。至少，这些媒体应该包括开始和停止，以及调整音量的功能。

**&lt;video&gt; 标签内的段落

这个叫做**后备内容** — 当浏览器不支持 &lt;video&gt; 标签的时候，它将会显示出来，它使我们能够对旧的浏览器做一些兼容处理。你可以添加任何后备内容，在这个例子中我们提供了一个指向这个视频文件的链接，从而使用户可以至少访问到这个文件，而不会局限于浏览器的支持。

### 多格式支持 {#多格式支持}

如果你尝试使用像 Safari 或者 Internet Explorer 这些浏览器来访问上面的链接。视频并不会播放，这是因为不同的浏览器对视频格式的支持不同。

像 MP3、MP4、WebM这些术语叫做**容器格式**。他们是用不同的方式来播放音频或者视频的 — 也就是说这些容器是用不同的音频轨道、视频轨道、元数据来呈现媒体文件的。

视频和音频都有不同的格式，如下:



MP4 容器通常包括 AAC 以及 MP3 音频和 H.264 视频。主要在 Internet Explorer 和 Safari 当中支持。

老式的 Ogg 容器往往支持 Ogg Vorbis  音频和 Ogg Theora 视频。主要在 Firefox 和 Chrome 当中支持，不过这个容器已经被更强大的 WebM 容器所取代。

音频播放器将会直接播放音频文件,，例如 MP3 和 Ogg 文件。这些不需要容器。

这并没有那么简单，你可以从这里看到 音视频编码兼容表。此外，许多移动平台的浏览器能够播放一些不支持的格式，但是它们用的却是底层系统的媒体播放器。但这也仅是现在支持。

以上的格式主要用于将音频和视频压缩成可管理的文件（原始的音频和视频文件非常大）。浏览器包含了不同的 Codecs,，如 Vorbis 和 H.264,，它们用来将已压缩的音频和视频转化成二进制数字。正如刚才所说，浏览器并不全支持相同的 codecs，所以你得使用几个不同格式的文件来兼容不同的浏览器。如果你使用的格式都得不到浏览器的支持，那么媒体文件将不会播放。

MP3 \(音频格式\) 和 MP4/H.264 \(视频格式\) 是被广泛支持的两种格式，并且质量良好。然而，他们却有专利的阻碍 — MP3 的专利会持续到2017年（就在我翻译这篇文章的当天，MP3专利解除了），而 H.264 会持续到2027年早期。意思也就是说浏览器若想要支持这些格式，就得支付高额的费用。此外，许多人反对软件技术垄断，支持开源的格式。这就是为什么我们需要准备不同的格式来兼容不同的浏览器。

`<video controls>

`  <source src="rabbit320.mp4" type="video/mp4">

`  <source src="rabbit320.webm" type="video/webm">

`  <p>你的浏览器不支持 HTML5 视频。可点击<a href="rabbit320.mp4">此链接</a>观看</p>

`</video>`

现在我们将 src 属性从 &lt;video&gt; 标签中移除，转而将它放在几个单独的标签 &lt;source&gt; 当中。在这个例子当中，浏览器将会检查 &lt;source&gt; 标签，并且播放第一个与其自身 codec 相匹配的媒体。你的视频应当包括 WebM 和 MP4 两种格式，这两种在目前已经足够支持大多数平台和浏览器。



### 其他 &lt;video&gt; 特性

`<video controls width="400" height="400"

`       autoplay loop muted

`       poster="poster.png">

`  <source src="rabbit320.mp4" type="video/mp4">

`  <source src="rabbit320.webm" type="video/webm">

`  <p>你的浏览器不支持 HTML5 视频。可点击<a href="rabbit320.mp4">此链接</a>观看</p>

`</video>`

新的特性：

**

你可以用属性控制视频的尺寸，也可以用 CSS 来控制视频尺寸。 无论使用哪种方式，视频都会保持它原始的长宽比 — 也叫做纵横比。如果你设置的尺寸没有保持视频原始长宽比，那么视频边框将会拉伸，而未被视频内容填充的部分，将会显示默认的背景颜色。

**autoplay

这个属性会使音频和视频内容立即播放，即使页面的其他部分还没有加载完全。建议不要应用这个属性在你的网站上，因为用户们会比较反感自动播放的媒体文件。

**loop

这个属性可以让音频或者视频文件循环播放。同样不建议使用，除非有必要。

**muted

这个属性会导致媒体播放时，默认关闭声音。

**poster

这个属性指向了一个图像的URL，这个图像会在视频播放前显示。通常用于粗略的预览或者广告。

**preload

这个属性被用来缓冲较大的文件，有3个值可选：



"auto" ：页面加载后缓存媒体文件

"metadata" ：仅缓冲文件的元数据

注意我们并没有使用 autoplay 属性在这个版本的例子中 — 如果当页面一加载就开始播放视频的话，就不会看到 poster 属性的效果了。

### &lt;audio&gt; 标签 {#<audio>_标签}

&lt;audio&gt; 标签与 &lt;video&gt; 标签的使用方式几乎完全相同，有一些细微的差别比如下面的边框不同

`<audio controls>

`  <source src="viper.mp3" type="audio/mp3">

`  <source src="viper.ogg" type="audio/ogg">

`  <p>你的浏览器不支持 HTML5 音频，可点击<a href="viper.mp3">此链接</a>收听。</p>

`</audio>`

音频播放器所占用的空间比视频播放器要小，由于它没有视觉部件 — 你只需要显示出能控制音频播放的控件。一些与 HTML5 &lt;video&gt; 的差异如下：



同时也不支持 poster 属性 — 同样，没有视觉部件。

除此之外，&lt;audio&gt; 标签支持所有 &lt;video&gt; 标签拥有的特性

## 显示音轨文本 {#显示音轨文本}

许多人不想（或者不能）听到 Web 上的音频/视频内容，至少在某些情况下是这样的，比如：



另外的情况可能是由于人们并不能听音频，可能是因为他们在一个非常嘈杂的环境当中（比如在一个拥挤的酒吧内恰好赶上了球赛 ），也可能是由于他们并不想打扰到其他人（比如在一个十分安静的地方，例如图书馆）。

有一些人他们不说音频当中的语言，所以他们听不懂，因此他们想要一个副本或者是翻译来帮助他们理解媒体内容。

给那些听不懂音频语言的人们提供一个音频内容的副本岂不是一件很棒的事情吗？所以，感谢 HTML5 &lt;video&gt; 使之成为可能，有了 **WebVTT 格式**，你可以使用 **&lt;track&gt;** 标签。

 “副本”的意思是指，用文本记录下音频的内容。

WebVTT 是一个格式，用来编写文本文件，这个文本文件包含了众多的字符串，这些字符串会带有一些元数据，它们可以用来描述这个字符串将会在视频中显示的时间，甚至可以用来描述这些字符串的样式以及定位信息。这些字符串叫做 **cues** ，你可以根据不同的需求来显示不同的样式，最常见的如下：



通过添加翻译字幕，来帮助那些听不懂外国语言的人们理解音频当中的内容。

captions

同步翻译对白，或是描述一些有重要信息的声音，来帮助那些不能听音频的人们理解音频中的内容。

timed descriptions

将文字转换为音频，用于服务那些有视觉障碍的人。

一个典型的 WebVTT 文件如下：

`WEBVTT

`

`00:00:22.230 --> 00:00:24.606

`第一段字幕

`

`00:00:30.739 --> 00:00:34.074

`第二段

`

让其与 HTML 媒体一起显示，你需要做如下工作：



用 &lt;track&gt; 标签链接 .vtt 文件， &lt;track&gt; 标签需放在 &lt;audio&gt; 或 &lt;video&gt; 标签当中，同时需要放在所有 &lt;source&gt; 标签之后。使用 kind 属性来指明是哪一种类型，如 subtitles 、 captions 、 descriptions。然后，使用 srclang 来告诉浏览器你是用什么语言来编写的 subtitles。

`<video controls>

`    <source src="example.mp4" type="video/mp4">

`    <source src="example.webm" type="video/webm">

`    <track kind="subtitles" src="subtitles_en.vtt" srclang="en">

`</video>`

文本轨道会使你的网站更容易被搜索引擎抓取到 （SEO）， 由于搜索引擎的文本抓取能力非常强大，使用文本轨道甚至可以让搜索引擎通过视频的内容直接链接。






