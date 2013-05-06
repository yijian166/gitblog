---
layout: post
title: 盒模型和定位
categories: [html-css]
---

{{ page.title }}
================

<p class="meta">LESSON 3 · 2013/04/23</p>

在HTML和CSS中需要彻底理解的一个概念便是盒模型。盒模型概念中声明了页面中的每个元素都是一个矩形盒子，可能会包含外边距（margin），内边距（padding）和边框（border）。

再重复一遍，**页面中每个元素都是一个矩形盒子**。

对盒模型有一个基本了解至关重要，因为网站建设主要依赖它。若想要创建更为主流的网站，就需要对盒模型有一个更深入的了解，尽管令人沮丧的是，这有点难度。另外为了布局网页，了解不同元素的定位方式也同等重要。根据内容和上下文环境，定位元素的方法到是有几个。

###盒子尺寸

到现在，你已经意识到在页面中的元素，无论是块级还是行内元素都是一个矩形盒子。元素盒子有不同的尺寸，或许还有`margin`，`padding`和`border`这些也会影响盒子的尺寸。把这些属性聚在一起就叫*盒模型*。让我们一并学习下盒模型和这些CSSS属性来更好的了解HTML和CSS。

![盒模型示例](http://learn.hicc.me/images/2013/04/square-elements.jpg)

上图中所示的即是每个元素的矩形盒子（不管每个元素的实际形状）。

##盒模型

正如之前说过的，每个元素都是一个矩形盒子，包括`width`，`height`，可能还会包括`margin`，`padding`，`border`。所有的值算到一块便构成了所谓的[盒模型](http://css-tricks.com/the-css-box-model/)。

盒子首先以元素的`width`和`height`开始，宽和高可由元素的类型，元素内类容，或者指定的`width`和`height`属性决定。随后便是元素的`padding`和`border`。紧跟`border`的便是`margin`，在技术上来讲`margin`不包括在盒子的实际尺寸中，但`margin`确实帮忙定义了盒子模型。
<pre><code class="language-css">
div {
	background: #fff;
	border: 6px solid #ccc;
	height: 100px;
	margin: 20px;
	padding: 20px;
	width: 400px;
}
</code></pre>

分解一个元素，包括盒模型的总宽，使用如下公式：
`margin-right` + `border-right` + `padding-right` + `width` + `padding-left` + `border-left` + `margin-left`

类似的，总高公式：
`margin-top` + `border-top` + `padding-top` + `height` + `padding-bottom` + `border-bottom` + `margin-bottom`

![盒模型分解](http://learn.hicc.me/images/2013/04/box-model.png)

使用上述公式，上图例中的宽高为：

**宽**：`492px` = `20px` + `6px` + `20px` + `400px` + `20px` + `6px` + `20px`

**高**：`192px` = `20px` + `6px` + `20px` + `100px` + `20px` + `6px` + `20px`

让我们看看盒模型中的每个属性

##`height`和`width`

每个元素都有一个继承的`height`和`width`属性，而根据元素的不同目的，你可能需要对元素默认的`height`和`width`做调整。如果一个元素是页面布局与设计的关键，那么你很可能会对其赋予特定的`height`和`width`，这样**块级元素**的宽高默认值可能会被覆盖。

###CSS中`height`属性

元素默认的`height`属性由其内容决定。在垂直方向上所有元素都会尽可能的伸缩来适应内容。给一个**块级**元素设置一个特定的高度则需要使用`height`属性。
<pre><code class="language-css">
div {
	height: 100px;
}
</code></pre>

###CSS中`width`属性

一个元素的`width`取决于它的显示类型。块级元素的`width`默认100%，它会铺满可用的整个横向空间。行内元素则是在横向方向尽可能的伸缩来适应内容。因为行内元素尺寸不可更改，CSS中`width`和`height`值只能在**块级**元素上起作用。
<pre><code class="language-css">
div {
	width: 400px;
}
</code></pre>

##`margin`和`padding`

每个浏览器都给元素应用了一个基本的`margin`和`padding`值来使得元素易读和易于区别。每个浏览器的各个元素的值都不一样。在Lesson 1 中介绍过使用[css reset](../html-css/terminology-syntax-introduction.html)将这些值充值为零。使用重置样式使得我们可以在统一的基础上开始工作，也就容许我们进一步的设置特定元素的属性值。

###CSS中`margin`值

给元素设置`margin`属性，即在元素的四周设置了一段空间。`margin`的值即外边据处在边框的外面完全透明。可以用`margin`来将元素定位到页面中特定的位置或者是将所有的元素隔开，给元素提供一个呼吸的空间。
<pre><code class="language-css">
div {
	margin: 20px;
}
</code></pre>

###CSS中`padding`值

`padding`和`margin`十分相像，只是`padding`处于元素边框的里面。`padding`值也就是内边距继承元素的背景，用来给元素内部提供空间，并不和`margin`一样用来定位元素。
<pre><code class="language-css">
div {
	padding: 20px;
}
</code></pre>

![margin和padding](http://learn.hicc.me/images/2013/04/margin-padding.png)

上图展示了盒模型中使用`margin`将元素相互间隔开，使用`padding`来设置元素内空间。

###`margin`和`padding`的声明

`margin`和`padding`的值支持简写和完整写法。给元素的四个方向的`margin`和`padding`设置同样的值只需这样：
<pre><code class="language-css">
div {
	margin: 20px;
}
</code></pre>

元素顶部和底部的值相等，左右方向的相等只需设置连个值，顶部和底部的写在前面。
<pre><code class="language-css">
div {
	margin: 10px 20px;
}
<code></pre>

若元素的四个方向值不同，则四个值按照top,right,bottom,left的顺序声明。
<pre><code class="language-css">
div {
	margin: 10px 20px 0 15px;
}
</code></pre>

另外，你还可以使用单独的属性一次只设置一个方向的值。每个属性以`margin`或者`padding`开始中间连字符然后紧跟需要设置的方向（`top`,`right`,`bottom`,`left`）。例如`padding-left`使用一个值，设置了元素左边的内边距。
<pre><code class="language-css">
div {
	margin-top: 10px;
	padding-left: 6px;
}
</code></pre>

##`border`

边框处在元素内边据和外边据之间，设置了元素的轮廓。边框的设置需要三个值，宽度，样式，和颜色。简写模式中按照宽度（width），样式（style），颜色（color）的顺序即可。完整模式则分解为三个属性`border-width`，`border-style`和`border-color`。

一般见到的都是单位宽度，实线，单色的边款，但[边框](http://www.quackit.com/html/codes/html_borders.cfm)支持不同尺寸多色多样式。
<pre><code class="language-css">
div {
	border: 6px solid #ccc;
}
</code></pre>

<div class="code-box">
	<h4>长度值</h4>
	<p>CSS中的外边据，内边距，边框有几种<a href="https://developer.mozilla.org/en/CSS/length">长度值</a>可供选择。</p>
	<p><strong>相对值</strong>相对于元素已使用的值。这些值包括<code>em</code>和百分百。</p>
	<p><strong>绝对值</strong>与元素无关维持一个固定值。这些值包括像素，点，英寸，厘米等。</p>
</div>

##元素浮动

讲完元素盒模型页面代码布局的革命只成功了一半。另一半就是如何合适的对齐页面中所有的元素。将一个元素定位到另一个元素边的方法之一便是使用`float`属性。`float`属性可以使元素左右浮动，是元素相互靠近或者定位到现对的位置。

拿一个通用的页面布局来说，默认情况下`section`和`aside`作为块级元素，布局是头尾相接。我们希望将两者靠边并排布局。只需给每个元素一个特定的`width`然后将一个左浮动，另一个由浮动，即可完成布局。

![通用页面布局](http://learn.hicc.me/images/2013/04/floats.png)

对于[浮动元素](http://coding.smashingmagazine.com/2007/05/01/css-float-theory-things-you-should-know/)有几个重要的地方需要注意。首先是，当一个元素设置浮动之后，它会浮动紧靠到父元素容器的边界，如果该元素没有父元素，它就会浮动到页面容器的边界。其次，一个元素浮动之后，页面正常流里面的其他元素会环绕该元素。
<pre><code class="language-css">
section {
	float: left;
	margin: 10px;
	width: 600px;
}
aside {
	float: right;
	margin: 10px;
	width: 320px;
}
</code></pre>
###清除元素浮动

当一个元素浮动之后，它会打破页面正常的文档流，其他的元素会尽可能的环绕这个浮动的元素。有时候这是好事，例如当图片浮动到块级内容的边界，但有时候这并不是好事。

当一个元素，或者几个元素浮动之后，你可以使用`clear`属性来使文档流恢复到正常。给每个需要回到正常文档流的元素使用`clear`属性。

在上面的例子中，`section`和`aside`浮动。我们给`footer`元素使用`clear`属性迫使它回到正常的文档流——定位到俩个浮动元素的下面。
<pre><code class="language-css">
footer {
	clear: both;
}
</code></pre>

##元素定位（`postion`）

除了元素浮动，你还可以使用`postion`属性来定位元素。`postion`属性有几个不同的值，每个值都有[不同的功能](http://www.alistapart.com/articles/css-positioning-101/)。

`postion`属性的默认值是`static`，表示维持元素在正常的文档流中。`relative`值容许你使用盒子偏移属性（`top`，`right`，`bottom`和`left`）。`absolute`和`fixed`同样配合盒子偏移属性使用，但是使用这连个属性之后元素便不再正常的文档流中，而且这两个属性相对于`postion`属性值为`relative`的父元素。

![绝对定位示例](http://learn.hicc.me/images/2013/04/floats.png)

在上图的例子中，`header`指定了`postion`属性值为`relative`，它便作为一个静态的容器，其内的绝对定位子元素便基于它定位。因此绝对定位的`ul`元素上下相对于静态容器`header`偏移`10px`。

图示例子的代码为：
HTML
	<header>
  		<ul>...</ul>
	</header>

CSS
<pre><code class="language-css">
header {
	position: relative;
}
ul {
	position: absolute;
	right: 10px;
	top: 10px;
}
</code></pre>

###盒子偏移（offset）属性

只要元素的`postion`不设置为`relative`，元素即可使用偏移属性。这些属性包括`top`，`right`，`bottom`和`left`。根据属性，他们使元素在对应方向偏移。

例如，`bottom: 32px;`将会使元素定位到离父元素（`postion`属性为`relative`）底部32px的位置。对应的，`bottom: -32px;`将会定位元素在父元素底部32px的位置。

<div class="code-box">
	<h4>网格和框架</h4>
	<p>在站点布局的时候有许多的工具和实践经验可以使用，网格和框架无疑最值得使用</p>
	<p><strong>网格</strong>,包括横向和纵向网格，网格可以使得你的网站所有元素对齐，且富有韵律。在此有几个<a href="http://vandelaydesign.com/blog/design/resources-grid-based-design/">值得推荐的</a>，且在近几年流行的网格可以使用，你可以选择其中的一种或者创建你自己的网格，只要适合你的项目即可。</p>
	<p><strong>框架</strong>可以让在一个预先定义的标准上快速地建设网站。根据项目，框架可以提供一个很好的开始，甚至可以提供一个完整解决方案，也可能带来的麻烦比他的价值还多。在你头脑发热之前，你最好研究下选用的框架，看看你是否能在它上面愉悦的工作和编辑。</p>
</div>

##资源

<ul>
  <li><a href="https://developer.mozilla.org/en/CSS/length" rel="nofollow">CSS Length Values</a> via Mozilla Developer Network</li>
  <li><a href="http://www.quackit.com/html/codes/html_borders.cfm" rel="nofollow">HTML Borders</a> via Quackit.com</li>
  <li><a href="http://css-tricks.com/the-css-box-model/" rel="nofollow">The CSS Box Model</a> via CSS-Tricks</li>
  <li><a href="http://coding.smashingmagazine.com/2007/05/01/css-float-theory-things-you-should-know/" rel="nofollow">CSS Float Theory</a> via Smashing Magazine</li>
  <li><a href="http://www.alistapart.com/articles/css-positioning-101/" rel="nofollow">CSS Positioning 101</a> via A List Apart</li>
  <li><a href="http://vandelaydesign.com/blog/design/resources-grid-based-design/" rel="nofollow">Resources for Grid-Based Design</a> via Vandelay Design</li>
</ul>