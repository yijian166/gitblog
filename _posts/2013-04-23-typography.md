---
layout: post
title: 排版
categories: [html-css]
---

{{ page.title }}
================

<p class="meta">LESSON 4 · 2013/04/23</p>

近几年，网页排版有了实质性的发展，倒是有几个不同的原因使网页排版如此流行，但最大原因还是你可以在页面上使用你自己的web fonts。

在此之前，设计师在网页设计只能使用很少的几个字体。他们只能使用电脑中预先安装的最普遍的字体，因为只有这样页面才能在屏幕上正确的显示。而现在页面中可以嵌入字体，设计师便有了更多的选择。

页面上的字体嵌入为所有的字体打开了一扇门，这也就需要设计师懂得一些基本的排版规则，并能够将这些规则转化成HTML和CSS代码，以此来创建线上的排版的核心和[文本样式](http://dev.opera.com/articles/view/29-text-styling-with-css/)。

<div class="code-box">
<h4>字形（Typeface）vs.字体（font）</h4>
<p>typeface和font这两个术语经常互用，也经常引起混乱。下面就分析下这两个术语究竟指的是什么，也希望所给的示例你能够明白并使用。</p>
<p><strong>typeface</strong>指的是你所看见的字形，它是一种文本表现，感受，阅读的艺术印象。</p>
<p><strong>font</strong>则指的是字体文件。电脑使用字体文件（font）在屏幕上渲染成字形（typeface）</p>
<p>另一个类似的例子（<a href="http://fontfeed.com/archives/font-or-typeface/">歌曲和MP3文件</a>）可以帮助你分清两者的区别.typeface就类似与歌曲，歌曲是一种艺术成果，是有艺术家在演出中所创造的。而font则类似于MP3文件，MP3文件并不是一种艺术印象，它只是艺术价值的载体。</p>
</div>

##格式化的内容

在之前[元素和语义化](../elements-semantics.html)的教程中，我们提到过怎样语义化地构建页面的内容。这篇教程是本文不可或缺的一部分，因此值得复习一下其中的内容。而在此就简单对标题、段落以及怎么样变粗和倾斜文本做一个简单的回顾。

###标题

共有6个不同级别的标题元素，`h1`到`h6`，每个标题都是作为前一标题的补充性的标题，现对于其他标题元素，`h1`应该用于大的、更为重要的标题。在合适的情景下使用HTML5的结构性元素，标题元素则可以重复使用。

	<h1>Lorem ipsum dolor sit amet...</h1>
	<h2>Pellentesque habitant morb...</h2>

###段落

段落元素，简单来说是页面中内容增加段落的完美选择。每个段落都应该以`<p>`起始以`</p>`结束。

	<p>Id quil una virtute ponunt...</p>

###粗体文本

可以使用`strong`元素来让文本变粗，`strong`元素不仅能使文本变粗，在语义上它表示页面中较为重要的文本。

	<p>Duis in <strong>voluptate</strong> velit cillum.</p>

###斜体文本

斜体文本通过`em`元素来实现。而`em`元素在语义上表示有强调意味的文本。

	<p>Quae vivendi <em>putanda</em> est, expeteretur nih.</p>

