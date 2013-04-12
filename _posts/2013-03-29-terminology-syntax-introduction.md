---
layout: post
title: 术语、语法和介绍
---

{{ page.title }}
================

<p class="meta">2013/03/29</p>
###LESSON 1

在开始本教程之前，我们最好能够搞明白这两个语言的语法和一些一般的的术语。

概括来说，HTML是一种超文本标记语言用来给内容赋予结构和意义，CSS也被称为层叠样式表，是一种描述性语言，赋予内容样式及外观。

简单来说便是，HTML决定了网页上内容的结构和意义，而CSS则决定了内容的样式和外观。这两种语言相互独立，CSS不应该存在在HTML文件里面，反之亦然。

将这个概念讲的远点来说，HTML中的`p`元素被用来显示网上的文本段落。`p`元素专门用在这里是因为它为内容提供了最大的意义，因此`p`元素是最语义的元素。让后CSS则使用类型选择器`p`来定义此段落的颜色、字体大小、字体粗细以及其他文本属性，其他的属性也可定义再此。

####HTML基础术语

初次接触HTML你会听到很多新的、陌生的术语，随着时间推移你会慢慢熟悉所有的术语，但是今天你需要学习三个基本的术语：标签、元素和属性。

#####元素

元素是定义页面内对象结构和内容的指示符，比较常见的有 `h1` 到 `h6`  , `p` , `a` , `div` , `span` , `strong` , `em`。


	<a>

#####标签

元素通常由标签成对组成——开始标签以及闭合标签。开始标签标记了元素的开始，例如`<div>` 。闭合标签标记了一个元素的结束，标签内以一个斜杠开始，例如`</div>`。



	<a> ... </a>


#####属性

属性是用于给元素提供额外指令，通常情况，属性用来给一个元素分配 id 、class、或者title，给媒体元素资源路径（src），或者提供一个超链接（href）。


	<a href="http://learn.hicc.me">HTML&CSS基础教程</a>

<div class="code-box">
	<h4>普通HTML术语例子</h4>
	<p><a href="http://share.9ikblog.com">飞鸟分享</a></p>
</div>

####HTML文档结构和语法

所有的HTML文档都需要一个必须的结构，它包含以下的申明和标签：`doctype`,`html`,`head`和`body`。

`doctype`申明用于通知web浏览器HTML所使用的版本，它位于HTML文档的最前面也就是文档一开始的地方。而紧跟着`doctype`申明的`html`标签则意味着文档的开始和结束。

文档的`head`则用于概括文档的所有元数据，文档的`title`，所有外部文件的连接。`head`标签中所有的内容在实际的web页面中都**不可见**。在web页面中所有可将的内容都在`body`中。

如下便是一般HTML文档的样子：

	<!DOCTYPE html>
	<html lang="en">
  	<head>
    	<meta charset="utf-8">
    	<title>Hello World</title>
  	</head>
  	<body>
    	<h1>Hello World</h1>
    	<p>This is a website.</p>
  	</body>
	</html>

####基础的CSS术语

除HTML术语之外，在此还有一些基础性的[CSS术语](http://www.codestyle.org/css/Glossary.shtml)你需要了解。随着HTML和CSS的熟练使用，你会对这些属性越发熟稔。

#####选择器

一个CSS选择器决定了对应的样式被精确地应用到哪个元素或者哪些元素。选择器可以组合包含不同的ID，class，type，以及其他的属性——一切都取决于你的具体所需。第一个大括号{之前的都属于CSS选择器。

	p { … }

#####属性

一个属性决定了所应用元素的样式。属性被定义为冒号之前的文本，CSS现已有大量丰富的属性可以被使用，而且不断有新的属性增加。

	p {
  	color: #ff0;
  	font-size: 16px;
	}

#####值

一个值决定了对应属性的行为。值被定义为冒号和分号之间的文本。

	p {
  	color: #ff0;
  	font-size: 16px;
	}

####CSS的结构和语法

CSS使用选择器将样式应用到HTML元素。所有的CSS样式都可以叠加，允许不同的样式被多重的元素所继承。

举一个例子，可以为一个页面的所有文本设置特定的颜色、大小、粗细。然后使用一个更有针对性的选择为一个单独的元素重设样式。

![CSS语法概要](http://learn.hicc.me/images/selector.png)

下面实例中语法实例了如何将样式用到所有的段落。

	p {
  	color: #ff0;
  	font-size: 16px;
	}

#####完整模式vs简写模式

在CSS中一个属性值的申明有很多种方法。使用完整模式，你一个接一个的堆砌每个属性和值。而使用间歇模式你只需为一个属性列出多个值即可。简写模式只需少量的代码因此推荐使用。不是所有的CSS属性都支持简写模式，因此你需要确保使用正确的属性值结构。


	/* Long Hand */
	p {
  	padding-top: 10px;
  	padding-right: 20px;
  	padding-bottom: 10px;
  	padding-left: 20px;
	}
	/* Short Hand */
	p {
  	padding: 10px 20px;
	}
	/* Short Hand */
	p {
  	padding: 10px;
	}

<div class="code-box">
	<h4>HTML和CSS中的注释</h4>
	<p>HTML和CSS允许你在代码内注释。这些注释可以被用来帮助组织，设置提醒，并更有效的管理代码。当有多个人协作开发同一份代码的时候注释便显得更为重要。任何注释内的文本将不会在实际的页面中出现。</p>
<p>**HTML注释** 使用`<!--`开始和`-->`结束来包裹注释内容。**CSS注释** 使用`/*`开始和`*/`结束来包裹注释内容</p>
</div>

####选择器

选择器，正如上文提及的，决定了那些元素会被施加样式。因此完全理解如何使用选择器和选择合适的选择器十分的重要。经常使用的选择器包括：元素、ID、class、或者三者的组合。

#####类型选择器

类型选择器属于最基本的选择器。非常的简单，类型选择器被用于将样式应用到不带任何必要属性的元素上面。从代码简洁和易于管理方面来考虑，属性选择器是首选。

HTML
	<p>...</p>

CSS
	p { ... }

#####类选择器

类（class）选择器允许将相同的样式应用到所有带同一个类属性的元素上。在CSS中将类名前面加个点号来标示类选择器。在HTML文档中不同的元素允许使用同样的类属性。

HTML

	<div class="awesome">...</div>

CSS
	
	.awesome { ... }

#####ID 选择器

ID选择器有点像类选择器，只是Id选择器一次只能针对一个特定的元素。ID选择器自然使用ID属性。类选择器使用点号表示，在CSS中在ID名前面加一个井号来标示ID选择器。每个文档中一个ID属性只容许使用一次，ID属性应该用于较为重要的元素。

HTML
	
	<div id="shayhowe">...</div>

CSS
	
	#shayhowe { ... }

#####组合选择器

CSS的漂亮之处在于选择器能够组合并且样式能够继承。因此你可以首先定义通用的选择器，在必要的时候以你的方式定义更为具体的，此外你可以将不同的选择器组合成你想要的更为具体的选择器。

	ul#social li {
  	padding: 0 3px;
	}
	ul#social li a {
  	height: 17px;
  	width: 16px;
	}
	ul#social li.tumblr a {
  	background: url('tumblr.png') 0 0 no-repeat;
	}

#####其他选择器

CSS选择器非常的强大，而上面的选择器概述只是个开始。还有许多[高级选择器](http://coding.smashingmagazine.com/2009/08/17/taming-advanced-css-selectors/)可随时使用。在你随机将class属性和id属性赋予元素之前你可以考虑其他的选择器是否能够更好完成你的目的。在此值得提及的是不是高级选择器并没有得到每个浏览器的支持，特别是在CSS 3中才被提出的选择器。如果你的高级选择器没有工作你可以检查该浏览器对其的支持。

####CSS的引用

在你的内容完成之际你或许想要用CSS样式化你的HTML。有几个不同方式来引用CSS，而且这些方法存在优劣之分。

最好的方式是在你页面头部引入一个包含你所有的样式外部样式表。使用一个外部样式表允许你同样的样式可以被用在整个网站，而且这样可以很快更彻底的改变网站。

其他的选择有内部样式和内联样式。而这些不推荐的原因是，这些方式将会导致网站的更新变得频繁而笨重。

	<!-- External CSS File -->
	<link rel="stylesheet" href="file.css">
	<!-- Internal CSS -->
	<style type="text/css">
	p {
  	color: #f60;
  	font-size: 16px;
	}
	</style>
	<!-- Inline CSS -->
	<p style="color: #f60; font-size: 16px;">Lorem ipsum dolor sit amet...</p>

#####使用外部CSS样式表

如上文中所说的，最好的CSS引入方式是使用一个外部样式表。如此你便可以在真个网站中使用一组样式。无痛的更改网站的样式，而且用户下载较少的数据即可保持整站的样式。

在HTML文档`head`元素内，`link`元素中值为`stylesheet`的`rel`属性定义了HTML文件和CSS文件之间的关系，此外`href`属性用来定义CSS文件的位置或者路径。

为了确保CSS能够渲染，`href`属性中的路径务必保持正确。正如上祢昂例子中所示，file.css和HTML文档一块被存储在根目录。

当CSS文件在子目录的情况下，`href`属性中的路径也需确保正确。例如，如果file.css存储在名为styles的子目录中，`href`属性中的路径则需设置为styles/file.css。

	<head>
  	<link rel="stylesheet" href="styles/file.css">
	</head>

####CSS重置

默认情况下每个web浏览器都有自己对不同元素样式化的解释。Chrome浏览器渲染输入栏的方式可能和IE浏览器的方式有很大的不同。在处理**浏览器兼容**上CSS重置被广泛的使用。
<div class="code-box”>
<h4>浏览器兼容和测试</h4>
<p>正如上面所言，不同的浏览器以不同的方式渲染页面。认识到浏览器兼容性性和测试的价值尤为重要。网站不必每个浏览器都表现一致，当至少要相近。根据你网站所看重的（兼容或者前卫？）你需要决定支持那些浏览器支持到什么程度。</p>
</div>

CSS重置包含了少数的规则集合，确保每个基础的HTML元素在不同浏览器中都有一个相同的样式。CSS重置包含了移除了所有的大小、margin、padding，以及其他的样式。重置需要处于CSS文件的最前面以此来最先渲染这样来确保其后的CSS样式能够被渲染到相同的页面骨架。

有数以千计的CSS重置可以选择，它们各有所长。我的最爱是[Eric Meyers reset](http://meyerweb.com/eric/tools/css/reset/),这个重置已经包含了最新的HTML5元素的重置，Eric的重置简短但正中要害，当然你也可以搜索你自己觉得合适的CSS重置。

<div class="code-box">
<h4>代码检测</h4>
<p>无论我们多么的精通，我们都会犯错。所幸当我们在书写HTML和CSS的时候有验证器可以检测我们的代码。W3C创建的[HTML](http://validator.w3.org/)和[CSS](http://jigsaw.w3.org/css-validator/)验证器可以扫描你的代码的错误。代码检测不仅让我们代码有正确的渲染，而且还可以交给你最好的代码书写方式。</p>
</div>

####资源

<ul>
  <li><a href="http://www.scriptingmaster.com/html/HTML-terms-glossary.asp" rel="nofollow">Common HTML Terms</a> via Scripting Master</li>
  <li><a href="http://www.codestyle.org/css/Glossary.shtml" rel="nofollow">CSS Glossary</a> via Code Style</li>
  <li><a href="http://coding.smashingmagazine.com/2009/08/17/taming-advanced-css-selectors/" rel="nofollow">Taming Advanced CSS Selectors</a> via Smashing Magazine</li>
  <li><a href="http://meyerweb.com/eric/tools/css/reset/" rel="nofollow">CSS Tools: Reset CSS</a> via Eric Meyer</li>
  <li><a href="http://www.shayhowe.com/web-design/intro-to-html-css/" rel="nofollow">An Intro to HTML <abbr title="and">&amp;</abbr> CSS</a> via Shay Howe</li>
</ul>






