# HTML表格高级特性和可访问性

## 使用 &lt;caption&gt; 为你的表格增加一个标题 {#使用_<caption>_为你的表格增加一个标题}

你可以为你的表格增加一个标题，通过 &lt;caption&gt; 元素，再把 &lt;caption&gt; 元素放入 &lt;table&gt; 元素中. 你应该把它放在&lt;table&gt; 标签的下面。

`<table>`

`  <caption>Dinosaurs in the Jurassic period</caption>`

``

`  ...`

`</table>`

标题意味着包含对于表格内容的描述，这对那些希望可以快速浏览网页中的表格对他们是否有帮助的读者们来说，是非常好的功能。特别是盲人用户，不需要让屏幕阅读设备读出很多单元格的内容，来让用户了解这张表格讲的是什么，而是可以依靠标题的内容，来决定是否需要了解更详细的内容。

注意: 这个 summary 属性也可以在&lt;table&gt; 元素中使用，用来提供一段描述，同样可以被屏幕阅读设备阅读。我们推荐使用 &lt;caption&gt; 元素来代替使用，因为 summary 被 HTML5 规范， deprecated \(废除了\)，也不能被视力正常的用户阅读。 \(它不会出现在页面上\)

## 添加 &lt;thead&gt;, &lt;tfoot&gt;, 和 &lt;tbody&gt; 结构 {#添加_<thead>_<tfoot>_和_<tbody>_结构}

由于你的表格在结构上有点复杂，如果把它们定义得更加结构化，那会帮助我们更能了解结构。一个明确的方法是使用 &lt;thead&gt;, &lt;tfoot&gt;,和 &lt;tbody&gt;, 这些元素允许你把表格中的部分标记为表头、表脚、正文部分。

这些元素不会使表格更易于屏幕阅读器用户访问，也不会造成任何视觉上的改变。然而，它们在应用样式和布局上会起到作用，可以更好地让 CSS 应用到表格上。给你一些有趣的例子，在长表格的情况下，你可以在每个打印页面上使表格页眉和页脚重复，你也可以让表格的正文部分显示在一个单独的页面上，并通过上下滚动来获得内容。

&lt;thead&gt; 需要嵌套在 table 元素中，放置在头部的位置，因为它通常代表第一行，第一行中往往都是每列的标题，但是不是每种情况都是这样的。如果你使用了 &lt;col&gt;/&lt;colgroup&gt; 元素，那么 &lt;thead&gt;元素就需要放在它们的下面。

 &lt;tfoot&gt; 需要嵌套在 table 元素中，放置在底部 \(页脚\)的位置，一般是最后一行，往往是对前面所有行的总结，比如，你可以按照预想的方式将&lt;tfoot&gt;放在表格的底部，或者就放在 &lt;thead&gt; 的下面。\(浏览器仍将它呈现在表格的底部\)

 &lt;tbody&gt; 需要嵌套在 table 元素中，放置在 &lt;thead&gt;的下面或者是 &lt;tfoot&gt; 的下面，这取决于你如何设计你的结构。\(&lt;tfoot&gt;放在&lt;thead&gt;下面也可以生效.\)

注意: &lt;tbody&gt; 总是包含在每个表中，如果你没有在代码中指定它，那就是隐式的。可以来验证一下，打开一个你之前没有包含 &lt;tbody&gt; 的例子，然后在你的 browser developer tools 中观察你的代码，你会看到浏览器为你添加了这个标签。你也许会想问，为什么你应该在所有表中都需要这个元素，因为它可以让你更好地控制表格结构和样式。

## 嵌套表格 {#嵌套表格}

在一个表格中嵌套另外一个表格是可能的，只要你包含完整的结构，包括 &lt;table&gt; 元素。这样通常是不建议的，因为这种做法会使标记看上去很难理解，对使用屏幕阅读的用户来说，可访问性也降低了。以及在很多情况下，也许你只需要插入额外的 单元格/行/列 到已有的表格中。然而有时候是必要的，比如你想要从其他资源中更简单地导入内容。

`<table id="table1">`

`  <tr>`

`    <th>title1</th>`

`    <th>title2</th>`

`    <th>title3</th>`

`  </tr>`

`  <tr>`

`    <td id="nested">`

`      <table id="table2">`

`        <tr>`

`          <td>cell1</td>`

`          <td>cell2</td>`

`          <td>cell3</td>`

`        </tr>`

`      </table>`

`    </td>`

`    <td>cell2</td>`

`    <td>cell3</td>`

`  </tr>`

`  <tr>`

`    <td>cell4</td>`

`    <td>cell5</td>`

`    <td>cell6</td>`

`  </tr>`

`</table>`

## 对于视力受损的用户的表格 {#对于视力受损的用户的表格}

一个表格可以是一个便利的工具，或者让我们快速访问数据，并允许我们查找不同的值。

为了理解信息，我们让数据与列标题或行标题之间建立视觉联系。

但假设你无法通过视觉关联这些数据呢? 那么你应该如何阅读上述的表格? 视力受损的用户经常使用一个屏幕阅读设备来为他们读出网页上的信息。对于盲人来说，阅读简单的文字没有什么问题，但是要理解一张表格的内容，这就有一些难度了。虽然，使用正确的标记，我们可以用程序化来代替视觉关联。

### 使用列和行的标题 {#使用列和行的标题}

屏幕阅读设备会识别所有的标题，然后在它们和它们所关联的单元格之间产生编程关联。列和行标题的组合将标识和解释每个单元格中的数据，以便屏幕阅读器用户可以类似于视力正常的用户的操作来理解表格。

### scope 属性 {#scope_属性}

 scope 属性，可以添加在&lt;th&gt; 元素中，用来帮助屏幕阅读设备更好地理解那些标题单元格，这个标题单元格到底是列标题呢，还是行标题。

`<thead>`

`  <tr>`

`    <th scope="col">Purchase</th>`

`    <th scope="col">Location</th>`

`    <th scope="col">Date</th>`

`    <th scope="col">Evaluation</th>`

`    <th scope="col">Cost (€)</th>`

`  </tr>`

`</thead>`

以及每一行都可以这样定义一个行标题

`<tr>`

`  <th scope="row">Haircut</th>`

`  <td>Hairdresser</td>`

`  <td>12/09</td>`

`  <td>Great idea</td>`

`  <td>30</td>`

`</tr>`

屏幕阅读设备会识别这种结构化的标记，并一次读出整列或整行，比如：

scope 还有两个可选的值 ： colgroup 和 rowgroup。这些用于位于多个列或行的顶部的标题。 如果你回顾一些文章开始部分的 "Items sold..." 表格。你会看到 "Clothes" 单元格在"Trousers", "Skirts", 和 "Dresses" 单元格的上面，且包括了它们三个。像 "Clothes" 这种单元格应该被标记为 \(&lt;th&gt;\)，但是 "Clothes" 是一个位于顶部的标题，且定义了其他三个子标题。 因此 "Clothes" 应该有一个 scope="colgroup"属性，而另外三个子标题应该用 scope="col"属性。

### id 和标题属性 {#id_和标题属性}

如果要替代 scope 属性，可以使用 id 和 headers 属性来创造标题与单元格之间的联系。使用方法如下:

为每个&lt;th&gt; 元素添加一个 id \(id 不能重复\)。

为每个 &lt;td&gt; 元素添加一个 headers 属性。每个 headers 属性需要包含 th 元素的 id 。 如果这个单元格是属于一个 th 元素下的，那么就需要包含 th 元素的 id 的值，如果属于多个 th 元素，那么可以用空格分隔这些 id。

这给你的HTML表格一个明确的定义，关于表格中每个单元格的位置。通过 headers 属性来定义属于哪些行或列。像一个电子表格，为了正常工作，该表确实需要列和行标题。

`<thead>`

`  <tr>`

`    <th id="purchase">Purchase</th>`

`    <th id="location">Location</th>`

`    <th id="date">Date</th>`

`    <th id="evaluation">Evaluation</th>`

`    <th id="cost">Cost (€)</th>`

`  </tr>`

`</thead>`

`<tbody>`

`<tr>`

`  <th id="haircut">Haircut</th>`

`  <td headers="location haircut">Hairdresser</td>`

`  <td headers="date haircut">12/09</td>`

`  <td headers="evaluation haircut">Great idea</td>`

`  <td headers="cost haircut">30</td>`

`</tr>`

``

`  ...`

``

`</tbody>`

注意: 这个放进为标题单元格和数据单元格之间创造了非常精确的联系。但是这个方法使用了大量的标记，所以容错率比较低。使用 scope 的方法对于大多数表格来说，也够用了。





