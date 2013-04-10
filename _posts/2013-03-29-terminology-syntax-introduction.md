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

<div class="code">
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

除HTML术语之外，在此还有一些基础性的[CSS术语](http://www.codestyle.org/css/Glossary.shtml)你需要了解。越使用HTML和CSS，你就会对这些属于越发的熟稔。

#####选择器






