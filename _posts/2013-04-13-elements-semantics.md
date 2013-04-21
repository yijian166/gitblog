---
layout: post
title: 元素和语义化
---

{{ page.title }}
================

<p class="meta">LESSON 2 · 2013/04/13</p>

简单了解了HTML和CSS之后，是时候深入学习如何组合使用这两个语言了。

在开始创建一个网页之前你不但需要学习不同的类型的内容需要哪个HTML元素来显示，而且需要了解这些元素有什么样的表现，这样你才能得到想要的结果。

另外，一旦开始写代码你需做到尽可能的语义化。语义化的书写代码包括确保代码有组织性，并做出明确的决定。

##语义化概述

在此之前语义化已经被提到过很多次了，究竟什么才是语义化？[HTML中的语义化](http://boagworld.com/dev/semantic-code-what-why-how/)是一种赋予页面内容意义和结构的做法。语义化扮演了页面内容的**价值**，语义化**不仅仅**只是为了样式的考虑。使用语义化的代码有很多的好处，包括能够让电脑、屏幕阅读器、搜索引擎、以及其他的设备更加充分的阅读和理解网页。而且。语义化的代码更加容易管理和使用、能够很清楚的知道每块内容是关于什么。

##`div`和`span`

`div`和`span`元素用于HTML中不同内容的容器。作为通用的容器元素，它们并没有其他元素都有的意义或者语义价值。页面中段落是语义化的，是因为其中内容被`p`元素包裹，众所周知`p`元素代表段落。`div`和`span`并不拥有这样的语义，因此只是简单的容器。两者最常用的地方便是对网站元素针对性的使用CSS样式。

`div`属于块级元素一般用来标识网站中较大的部分，以此来辅助布局和设计。而`span`则属于行内元素一般用来标识块级元素（例如段落）中较小的文本部分。

<div class="code-box">
	<h3>块级（block）元素vs.行内（inline）元素</h3>
	<p>所有元素不是块级就是行内元素。它们有什么区别？</p>
	<p><strong>块级</strong>元素在页面中会另起一行，而且会铺满可用宽度。块级元素间可以相互嵌套，也可以包裹行内元素。</p>
	<p><strong>行内</strong>元素在页面内不会另起一行，它们处于正常的文档流中，维持所需的宽度。行内元素间也可以相互嵌套，但是行内元素不可以嵌套块级元素</p>
</div>

`div`和`span`元素在设置了class和id属性之后便有了附加的价值。为了样式给元素添加class或者id属性，这样也就区别了不同的`div`或者`span`元素。class或者id名的选择就需要考虑语义化了。class或者id属性最好选用和元素实际上下文有意义的值。

例如，如果你有一个橙色背景的`div`里面包含了一些社交媒体的链接，你首次可能选用"orange"作为你的class名。但是之后你将背景换成了蓝色，"orange"的class名便讲不通了。更好的，更为语义化的方案是，选用”social“这个关联`div`内容而不是样式的class名。

		<!-- div -->
		<div class="social">
  			<p>Lorem ipsum dolor sit amet...</p>
  			<p>Lorem ipsum dolor sit amet...</p>
		</div>
		<!-- span -->
		<p>Lorem ipsum dolor sit amet, <span class="tooltip">consectetur</span> elit.</p>

##排版

大量的在线内容完全基于文本。线上也有许多其他不同形式的媒体和内容，但文本占据了大多数。HTML中有许多的元素用来显示网页上的文本。在本篇文章我们只专注最常用，最语义化的元素。更为深入了解可以查看[本篇文章](#)。

###标题

标题属于块级元素，共有六个等级，`h1`到`h6`，是用户阅读页面的关键标识。标题快速将内容按照层级分块，同时标题也帮助搜索引擎检索和确定页面内容的价值。

标题应该用在相关有顺序的内容上。页面或者内容块中初级标题应该使用`h1`，若还有下级标题，应该使用紧跟其后的`h2`。标题应该用于分类而不是用于能够让文本变粗或者变大。

		<h1>这是一级标题</h1>
		<h2>这是二级标题</h2>
		<h3>这是三级标题</h3>

<div class="code-box">
		<h4>标题示例</h4>
		<h1>这是一级标题</h1>
		<h2>这是二级标题</h2>
		<h3>这是三级标题</h3>
</div>

###段落

标题之后通常会紧跟段落。段落使用块级元素`p`元素来定义。段落一个接一个的出现，以此来给页面填充信息。

		<p>我希望能够远走，逃离我的所知，逃离我的所有，逃离我的所爱。</p>
		<p>大多数的人以其愚笨生活在他们的生活之中。</p>

<div class="code-box">
	<h4>段落示例</h4>
	<p>我希望能够远走，逃离我的所知，逃离我的所有，逃离我的所爱。</p>
	<p>大多数的人以其愚笨生活在他们的生活之中。</p>
</div>

###`strong`粗文本

使用`strong`行内元素使文本变粗来表示重要。重要的是要理解`strong`和`b`在语义化上的区别，两者都可以使文本变粗，`strong`在语义上被用来表示文本很重要，而`b`在多数情况下只是用来使文本变粗，从另一个角度来说`b`的语义化意义只是使得文本在样式风格上有所偏移不同，而不应该使文本得到过多的注意。最好根据粗体文本的重要程度来选择使用那个标签。

		<p>Duis in <strong>voluptate</strong> velit esse cillum.</p>

<div class="code-box">
	<h4>粗体文本示例</h4>
	<p>Duis in <strong>voluptate</strong> velit esse cillum.</p>
</div>

###有强调意味的斜体文本

行内元素`em`使文本倾斜并且对其施加强调语气。和`strong`一样，HTML中有两个标签可以让文本倾斜。两者在语义化上有少许不同，`em`对文本施加强调语气，因此多被选用来倾斜文本，另外的选择是`i`,在语义化上只是表达一种与上下文不同的语气。同样的，最好根据倾斜文本的重要程度来选择使用那个标签。

		<p>Quae ars <em>putanda</em> est, expeteretur si nih.</p>

<div class="code-box">
		<h4>倾斜文本示例</h4>
		<p>Quae ars <em>putanda</em> est, expeteretur si nih.</p>
</div>

###超链接

互联网中核心的元素之一便是由锚建立的超链接。超链接由行内元素`a`来定义，`a`标签中还需要一个源来指向链接。其中的`href`属性也就是所谓的超链接引用，设定链接的最终能够达到的页面。

`a`元素属于行内元素，为了将页面的的块级内容变成链接，在HTML5中容许`a`元素包裹块级元素，尽管这打破了标准约定。

	<a href="http://share.9ikblog.com">飞鸟分享</a>

<div class="code-box">
		<a href="http://share.9ikblog.com">飞鸟分享</a>
</div>

###相对路径和绝对路径

链接最常见的两种方式包括链接到同一站点内的其他页面和链接到其他站点。路径也就是`href`属性的值决定了它们如何链接。

链接到同一站点内的其他页面需要**相对路径**，其中域名并不在`href`属性的值内。链接到同一站点的其他页面，`href`属性值只需包含要链接的页面，例如`/about.html`。若需要连接到子目录中的页面，同样只需在`href`属性值中反映即可，例如`about.html`页面位于`pages`目录中，相应的现对路径即为`/pages/about.html`。

连接到外部站点则需要**绝对路径**，其中`href`属性值必须包含全部的域名信息。链接到Google网站，`href`属性的值则为`http://google.com`，以`http`开头并且包含域名（在例子中为`.com`）。

		<!-- Relative Path -->
		<a href="/about.html">About</a>
		<!-- Absolute Path -->
		<a href="http://www.google.com/">Google</a>

###链接到邮箱地址

偶尔你也有链接到邮箱地址的需要。当点击完链接只有会打开默认的邮箱客户端并填充一些信息。最少信息的发送地址会被填写，而其他信息例如主题和正文或许也会填写。

创建一个连接到邮箱地址的链接，`href`属性值需要以`mailto:`开始紧跟收件地址。要创建一个地址为i@hicc.me邮箱链接，`href`的值为`mailto:i@hicc.me`。

另外，标题和正文也可以被添加。添加标题只需在邮箱地址紧跟`subject=`参数，单词之间使用`%20`隔开。添加正文则使用`body=`参数，单词间的空格同样用`%20`编码，换行则使用`%0A`。

连起来，将一封标题为“hello cc”正文为“This is awesome”的邮件发送给i@hicc.me，其链接的`href`值则为`mailto:i@hicc.me?subject=hello%20cc&body=This%20is%20awesome.`。需要注意的是邮箱地址和标题之间需要`?`隔开，标题和正文之间使用`&`隔开。

如需要添加跟多的信息，如抄送和秘密抄送的添加方式可以查看Joost de Valk的教程[The Full mailto Link Syntax](http://yoast.com/guide-mailto-links/)。

		<a href="mailto:i@hicc.me?subject=hello%20cc
&body=This%20is%20awesome.">Email Me</a>

<div class="code-box">
	<h4>邮件链接示例</h4>
	<a href="mailto:i@hicc.me?subject=hello%20cc
	&body=This%20is%20awesome.">Email Me</a>
</div>

###在新窗口中打开链接

在超链接中可以设定链接在哪里打开。经典的打开是在当前窗口打开，当然链接还可在新的窗口打开，将`target`属性的值设为`_blank`，单击时链接即可在新的窗口打开。`target`属性决定链接在哪里显示，而其值`_blank`这指定了在新窗口打开。

		<a href="http://share.9ikblog.com" target="_blank" >飞鸟分享			</a>

<div class="code-box">
	<h4>在新窗口打开链接示例</h4>
	<a href="http://share.9ikblog.com" target="_blank" >
		飞鸟分享
	</a>
</div>

###链接到页面内元素

偶尔也会看到一些仅仅是链接到页面中其他部分的简单链接，在某些站点中的能将用户带到页面顶部的“返回顶部”按钮就是这样的链接。

创建一个页面内链接你只需要赋予想要链接到的元素一个特定的ID，然后使用这个ID作为链接的`href`值。例如在`body`上设置ID属性为`main`,即可通过点击`href`属性值为`#main`的链接返回该页面的顶部。

		<a href="#awesome">Awesome</a>
		<div id="awesome">Awesome Section</div>

<div class="code-box">
	<h4>页内链接示例</h4>
	<a href="#awesome">Awesome</a>
	<div id="awesome">Awesome Section</div>
</div>

##HTML5结构化元素

HTML5中新增了几个[元素](http://dev.opera.com/articles/view/new-structural-elements-in-html5/)，这个新增的元素都是为了提高HTML语义化。在此之前，若要在页面中声明一个块级的部分你一般会使用`div`。而在HTML5中便可以选用其他的更为语义化的块级元素。

![HTML5中新增的几个结构化元素](http://learn.hicc.me/images/2013/04/HTML5.png)

###`header`

`header`，正如其字面意义，用来标示页面、文章、章节、亦或页面其他部分的头部。一般而言，`header`中会包括标题，介绍文本，或者导航栏。在页面中你可以在多处使用`header`标签。在一个站点中，理想情况是页面的最开始会有一个`header`元素。另外必要情况下`header`元素也可能会作为文章或者其他部分的头部出现。

		<header>...</header>

<div class="code-box">
	<h4><code>header</code>元素的几个要点<h4>
	<p><code>header</code>元素最好不要和<code>head</code>元素，标题元素（从<code>h1</code>到<code>h6</code>）相混淆。</p>
	<p><code>header</code>元素属于结构化元素，用来包裹页面的头部，只会在<code>body</code>元素中使用，而<code>head</code>元素用来包裹元数据，文档标题，或者外部文件的链接，并不在实际显示页面中出现。</p>
	<p>标题元素，从<code>h1</code>到<code>h6</code>，用来表示整个页面的层级标题。</p>
</div>

###导航




未完持续···