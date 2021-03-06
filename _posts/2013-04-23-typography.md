---
layout: post
title: 排版
categories: [html-css]
---

{{ page.title }}
================

<p class="meta">LESSON 4 · 2013/04/23</p>

英文原文：[Typography](http://learn.shayhowe.com/html-css/typography)

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

```html
<h1>Lorem ipsum dolor sit amet...</h1>
<h2>Pellentesque habitant morb...</h2>
```
###段落

段落元素，简单来说是页面中内容增加段落的完美选择。每个段落都应该以`<p>`起始以`</p>`结束。

```html
<p>Id quil una virtute ponunt...</p>
```

###粗体文本

可以使用`strong`元素来让文本变粗，`strong`元素不仅能使文本变粗，在语义上它表示页面中较为重要的文本。

```html
<p>Duis in <strong>voluptate</strong> velit cillum.</p>
```


###斜体文本

斜体文本通过`em`元素来实现。而`em`元素在语义上表示有强调意味的文本。

```html
<p>Quae vivendi <em>putanda</em> est, expeteretur nih.</p>
```

##文本颜色

一般来说设计师或者开发人员在创建网站的时候首先会选择文本颜色和字体，当然还有很多其他的属性需要更改，但文本颜色和字体这两项却可在对短时间内影响网页的整体感观。清楚浏览器的默认样式，使用自定义的文本颜色和字体既可以快速设置页面的风格。

设置文本颜色只需`color`属性即可。`color`属性只接受一个值，颜色值支持多种格式，支持关键词、十六进制的值、RGB、RGBa和HSLa，最常用的是十六进制的值，因为它可高效地控制颜色。为了支持颜色透明度，在CSS3中支持了RGBa值，但是不是所有浏览器都支持，因此最好能使用对应的十六进制值。

```css
body {
	color: #555;
}
```

<div class="code-box">
	<h4>颜色十六进制值的简易写法</h4>
	<p>颜色的十六进制值，支持简写模式。十六进制颜色由井号（#）紧跟六个字符组成。这些字符代表不同的颜色，经常成对出现，起始的两个字符，中间的，末尾的。若这每对中的字符相同，则整个值可简写成三个。例如颜色值<code>#555555</code>可简写成<code>#555</code>，<code>#ff6600</code>可简写成<code>#f60</code>。</p>
</div>

##字体属性

CSS中有许多属性用开编辑页面中文本的感观。这些属性可分为两类，针对`font`的和针对`text`的，而这两个类型的属性对应的大多以`font-`，`text-`开头。我们先讨论针对`font`字体的属性。

###`font-family`

`font-family`属性用来声明文本使用那个字体，那些备用字体。`font-family`属性包含了多个值，每个之间用逗号隔开。左边第一个所声明的，是首要选择的字体，若第一个声明的无法使用则从左往右选择备用字体。若字体名称包含两个或两个以上的单词，需要使用引号包起来。另外，最后的一个值应该是个关键词，指定了系统该类型下的默认字体。

```css
p {
	font-family: 'Helvetica Neue', Arial, Helvetica, sans-serif;
}
```

##`font-size`

`font-size`属性可以让我们使用通用的[长度值](http://css-tricks.com/css-font-size/)来控制文本中的字体大小，这些值可以是像素，em，百分制，以及`font-size`关键词。像素值能够精准地控制字体大小，因此别广泛使用。在之前，使用em和百分制较为合适，是因为当用户缩放浏览器中页面的时候设置这两个属性的字体也可以相对缩放。而现代浏览器大多都能够很好的缩放像素值。因此em和百分制的使用大大减少。

```css
p {
	font-size: 14px;
}
```

###`font-style`

`font-style`属性可以用来倾斜字体，或者将倾斜字体恢复正常。`font-style`属性接受四个关键词的值，包括`normal`，`italic`，`oblique`和`inherit`。这四个值中最常用的有`normal`和`italic`。`italic`可以使字体倾斜，而`normal`则让字体恢复正常。

```css
p {
	font-style: italic;
}
```

###`font-variant`

偶尔也需要将字体设置为小型大写或者小写，因此有了`font-variant`属性。
`font-variant`属性结构三个值，包括`normal`，`small-caps`和`inherit`。常见的用法是将小写设置`small-caps`或者将小型大写设置`normal`。若字体不支持小型大写，那么该文本使用`small-caps`将没有效果。因此使用这个属性之前请仔细检查所使用字体是否支持。

```css
p {
	font-variant: small-caps;
}
```


###`font-weight`

偶尔也需要将文字设置为粗体或者特定的粗细，此刻`font-weight`就派上了用场。一般来说，`font-weight`属性使用`normal`，`bold`，`bolder`，`lighter`和`inherit`这几个关键词。相对于其他关键词，推荐使用`normal`，`bold`将文本恢复或者设为粗体。

除此之外`font-weight`属性也支持数值类的值`100` `200` `300` `400` `500` `600` `700` `800` `900`。从最细的值`100`到最粗的`900`.这些值间粗细细分成了更多个等级，而不是简单的正常（`400`）和粗体（`700`）。在使用数值类值之前也需要检查所用的字体，尝试使用`100`细细的字体听起来是个不错的选择，但你的字体或许并没有这样的细度，属性也就不能生效。

```css
p {
	font-weight: bold;
}
```

###`line-height`

行高，也就是文本两线之间的距离，用`line-height`属性声明。`line-height`属性接受`font-size`所接受的值，通用的长度，以及数值。基于易读性的考虑，`line-height`最佳经验值为对应`font-size`值的1.5倍，这个可以通过设置`line-height`属性为150%来快速实现。但若你在使用基线网格，需要对行高有更精细的控制，`line-height`属性使用像素值则最为完美。

行高也可以用来使元素中单行文本垂直居中。设置元素的`line-height`值和`height`值相等即可使文本垂直居中。这个技巧大多用在按钮，警告文本，等一些单行块级文本中。

```css
p {
	line-height: 20px;
}
```

###字体属性简易写法

上面提到的针对字体的属性可以合并到`font`属性中作为[简写值](http://www.impressivewebs.com/css-font-shorthand-property-cheat-sheet/)，值的顺序从左到右依次为：`font-style` `font-variant` `font-weight` `font-size` `line-height` `font-family`，各个值之间无需逗号隔开，只需用空格即可，字体名称间用逗号隔开，`font-size`	和`line-height`之间使用间隔符`/`隔开。

值得一提的是，**除了**`font-size`和`font-family`属性，`font`属性中的其他值都是可选的，也就是说一般所见到的`font`属性中只有`font-size`和`font-family`属性值。

```css
p {
	font: italic small-caps bold 13px/20px 'Helvetica Neue',Arial, Helvetica, sans-serif;
}
```

<div class="code-box">
	<h4>字体属性示例</h4>
	<div>
		<h5>HTML</h5>
<div class="highlight">
	<pre>
		<code class="html language-html" data-lang="html">
<span class="nt">&lt;h2&gt;&lt;a</span> <span class="na">href=</span><span class="s">"#"</span> <span class="na">title=</span><span class="s">"Sample Blog Post Title"</span><span class="nt">&gt;</span>Sample Blog Post Title<span class="nt">&lt;/a&gt;&lt;/h2&gt;</span>
<span class="nt">&lt;p</span> <span class="na">class=</span><span class="s">"byline"</span><span class="nt">&gt;</span>Posted by Shay Howe on February 5th, 2012<span class="nt">&lt;/p&gt;</span>
<span class="nt">&lt;p&gt;</span>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla fringilla vehicula nisi vitae rutrum. Donec laoreet, arcu in elementum, dui mi auctor tortor, et lorem massa orci… <span class="nt">&lt;a</span> <span class="na">href=</span><span class="s">"#"</span> <span class="na">title=</span><span class="s">"Sample Blog Post Title"</span><span class="nt">&gt;</span>Continue reading →<span class="nt">&lt;/a&gt;&lt;/p&gt;</span>
</code></pre>
</div>
</div>
<div>
<h5>CSS</h5>
<div class="highlight"><pre><code class="css language-css" data-lang="css">
<span class="nt">h2</span><span class="o">,</span> <span class="nt">p</span> <span class="p">{</span>
<span class="k">color</span><span class="o">:</span> <span class="m">#555</span><span class="p">;</span>
<span class="k">font</span><span class="o">:</span> <span class="m">13px</span><span class="o">/</span><span class="m">20px</span> <span class="n">Arial</span><span class="o">,</span> <span class="s1">'Helvetica Neue'</span><span class="o">,</span><span class="s1">'Lucida Grande'</span><span class="o">,</span> <span class="k">sans-serif</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">a</span> <span class="p">{</span>
<span class="k">color</span><span class="o">:</span> <span class="m">#8ec63f</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">a</span><span class="nd">:hover</span> <span class="p">{</span>
<span class="k">color</span><span class="o">:</span> <span class="m">#f7941d</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">h2</span> <span class="p">{</span>
<span class="k">font-size</span><span class="o">:</span> <span class="m">22px</span><span class="p">;</span>
<span class="k">font-weight</span><span class="o">:</span> <span class="k">bold</span><span class="p">;</span>
<span class="k">margin-bottom</span><span class="o">:</span> <span class="m">6px</span><span class="p">;</span>
<span class="p">}</span>
<span class="nc">.byline</span> <span class="p">{</span>
<span class="k">color</span><span class="o">:</span> <span class="m">#8c8c8c</span><span class="p">;</span>
<span class="k">font-family</span><span class="o">:</span> <span class="n">Georgia</span><span class="o">,</span> <span class="n">Times</span><span class="o">,</span> <span class="s1">'Times New Roman'</span><span class="o">,</span> <span class="k">serif</span><span class="p">;</span>
<span class="k">font-style</span><span class="o">:</span> <span class="k">italic</span><span class="p">;</span>
<span class="p">}</span>
</code></pre>
</div>
</div>
<div>
		<h5>Demo</h5>
		<div class="code-box-2">
			<h2><a href="#" title="Sample Blog Post Title">Sample Blog Post Title</a></h2>
			<p class="byline">Posted by Shay Howe on February 5th, 2012</p>
			<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla fringilla vehicula nisi vitae rutrum. Donec laoreet, arcu in elementum, dui mi auctor tortor, et lorem massa orci… <a href="#" title="Sample Blog Post Title">Continue reading →</a></p>
		</div>
</div>
</div>


##文本属性

在了解了如何设置字体的字体类型，大小，样式，大小写，粗细以及行高，革命只成功了一半 ，还需要了解如何设置文本的对齐，装饰，首行缩进，变换，以及文字间距。

###文本对齐

文本对齐对构建一个有韵律且通畅的页面尤为重要，使用`text-align`属性即可设置文本对齐。`text-align`属性有五个值，包括`left` `right` `center` `justify` `inherit`。这些值都非常的简洁明了，其表现也如它们的字面意思。但是实用`text-align`属性不要和`float`属性混淆，`text-align`属性的值`left`和`right`使得元素内文本对齐，而`float`属性值`left`和`right`则移动整个元素。对`float`属性的更多介绍，可以查阅[盒模型和定位](../box-model-positioning.html)这篇文章。

```css
p {
  text-align: center;
}
```

###文本装饰

`text-decoration`属性提供了少量的几个方式来装扮文本。其接受以下几个关键词：`none` `underline` `over line` `line-thought` `blink` `inherit`。`text-decoration`属性常用在链接的下划线。虽然`blink`值存在，但因为它很容易让人分心，所以不推荐使用。而从语义化的角度，`line-thought`值可以使用`del`元素(用来标示该文本从文本移出)，或者`s`（用来标示该文本不再正确或关联）元素来替代。其他属性值可以随意使用。

···css
p {
  text-decoration: underline;
}
```

###文本缩进

`text-indent`属性可以让文本像印刷书中文本那样缩进。根据不同的值可以实现向内以及向外缩进。`text-indent`属性支持其他属性说使用的长度值，像素，点，百分制，等等。

```css
p {
  text-indent: 20px;
}
```

###文本阴影

`text-shadow`属性容许你给文本添加一个或者多个文本。其值从左往右依次四个。前三个值都是长度值，最后一个为颜色。前三个值中第一个决定了阴影的横向偏移，第二个值决定了阴影的纵向偏移，第三个则决定了阴影的模糊半径。第四个值也就是最后一个值是阴影的颜色，属性值`color`属性值一样。

文本阴影属性中使用逗号来隔开多个阴影值。给文本添加多个阴影可以使其置于文本上面或者下面，或者任何你想要的效果。

```css
p {
  text-shadow: 0 1px 0 rgba(0, 0, 0, 0.3);
}
```

###文本变换

`text-transform`属性和`font-variant`属性较为相似。`font-variant`属性用来设置字体内的大小写变换，而`text-transform`属性则用来改变整个文本的大小写。`text-transform`属性接受五个值：`none` `capitalize` `uppercase` `lowercase`以及`inherit`。

```css
p {
  text-transform: uppercase;
}
```

###字母间距

使用`letter-spacing`属性即可调整页面中文字的字距。使用正直或者负值你即可将字母间距调大或者调小。使用关键词`none`则可以将其恢复默认。`letter-spacing`属性中使用相对值则可以保证不同的文本都有着合适字距。当然你最好对文本进行双重验证。

```css
p {
  letter-spacing: -.5em;
}
```

###单词间距

和`letter-spacing`属性相似，还可以使用`word-spacing`属性调整单词间的间距。`word-spacing`属性值接受同样的长度或者关键字。并且将其应用到单词而不是字母。

```css
p {
  word-spacing: .25em;
}
```

<div class="code-box">
<h4>文本属性实例</h4>
<div>

<h5>HTML</h5>
<div class="highlight"><pre><code class="html language-html" data-lang="html"><span class="nt">&lt;h2&gt;&lt;a</span> <span class="na">href=</span><span class="s">"#"</span> <span class="na">title=</span><span class="s">"Sample Blog Post Title"</span><span class="nt">&gt;</span>Sample Blog Post Title<span class="nt">&lt;/a&gt;&lt;/h2&gt;</span>
<span class="nt">&lt;p</span> <span class="na">class=</span><span class="s">"byline"</span><span class="nt">&gt;</span>Posted by Shay Howe on February 5th, 2012<span class="nt">&lt;/p&gt;</span>
<span class="nt">&lt;p&gt;</span>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla fringilla vehicula nisi vitae rutrum. Donec laoreet, arcu in elementum, dui mi auctor tortor, et lorem massa orci… <span class="nt">&lt;a</span> <span class="na">href=</span><span class="s">"#"</span> <span class="na">title=</span><span class="s">"Sample Blog Post Title"</span><span class="nt">&gt;</span>Continue reading →<span class="nt">&lt;/a&gt;&lt;/p&gt;</span>
</code></pre>
</div>
<h5>CSS</h5>
<div class="highlight"><pre><code class="css language-css" data-lang="css"><span class="nt">h2</span><span class="o">,</span> <span class="nt">p</span> <span class="p">{</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#555</span><span class="p">;</span>
  <span class="k">font</span><span class="o">:</span> <span class="m">13px</span><span class="o">/</span><span class="m">20px</span> <span class="n">Arial</span><span class="o">,</span> <span class="s1">'Helvetica Neue'</span><span class="o">,</span> <span class="s1">'Lucida Grande'</span><span class="o">,</span> <span class="k">sans-serif</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">a</span> <span class="p">{</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#8ec63f</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">a</span><span class="nd">:hover</span> <span class="p">{</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#f7941d</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">h2</span> <span class="p">{</span>
  <span class="k">font-size</span><span class="o">:</span> <span class="m">22px</span><span class="p">;</span>
  <span class="k">font-weight</span><span class="o">:</span> <span class="k">bold</span><span class="p">;</span>
  <span class="k">letter-spacing</span><span class="o">:</span> <span class="m">-.9px</span><span class="p">;</span>
  <span class="k">margin-bottom</span><span class="o">:</span> <span class="m">6px</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">h2</span> <span class="nt">a</span> <span class="p">{</span>
  <span class="k">text-shadow</span><span class="o">:</span> <span class="m">1px</span> <span class="m">1px</span> <span class="m">0</span> <span class="m">#75a334</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">h2</span> <span class="nt">a</span><span class="nd">:hover</span> <span class="p">{</span>
  <span class="k">text-shadow</span><span class="o">:</span> <span class="m">1px</span> <span class="m">1px</span> <span class="m">0</span> <span class="m">#d48019</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">p</span> <span class="p">{</span>
  <span class="k">text-indent</span><span class="o">:</span> <span class="m">15px</span><span class="p">;</span>
<span class="p">}</span>
<span class="nc">.byline</span> <span class="p">{</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#8c8c8c</span><span class="p">;</span>
  <span class="k">font-family</span><span class="o">:</span> <span class="n">Georgia</span><span class="o">,</span> <span class="n">Times</span><span class="o">,</span> <span class="s1">'Times New Roman'</span><span class="o">,</span> <span class="k">serif</span><span class="p">;</span>
  <span class="k">font-style</span><span class="o">:</span> <span class="k">italic</span><span class="p">;</span>
  <span class="k">text-indent</span><span class="o">:</span> <span class="m">0</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">p</span> <span class="nt">a</span> <span class="p">{</span>
  <span class="k">font-size</span><span class="o">:</span> <span class="m">11px</span><span class="p">;</span>
  <span class="k">font-weight</span><span class="o">:</span> <span class="k">bold</span><span class="p">;</span>
  <span class="k">text-decoration</span><span class="o">:</span> <span class="k">underline</span><span class="p">;</span>
  <span class="k">text-transform</span><span class="o">:</span> <span class="k">uppercase</span><span class="p">;</span>
<span class="p">}</span>
</code></pre>
</div>
</div>
<div>
<h4>Demo</h4>
<div class="text">
<h2><a href="#" title="Sample Blog Post Title">Sample Blog Post Title</a></h2>
<p class="byline">Posted by Shay Howe on February 5th, 2012</p>
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla fringilla vehicula nisi vitae rutrum. Donec laoreet, arcu in elementum, dui mi auctor tortor, et lorem massa orci… <a href="#" title="Sample Blog Post Title">Continue reading →</a></p>
</div>
</div>
</div>



##网页安全字体

电脑、平板、手机或者其他可浏览网页设备中默认安装几个特殊字体。因此在站点中使用这些预装字体，无论使用什么设备访问站点，字体都能够被很好的渲染。这些字体即就是所谓的“网页安全字体”。网页安全字体只有少数的几个，其中最安全如下列。

<ul class="list-2">
  <li>Arial</li>
  <li>Courier New, Courier</li>
  <li>Garamond</li>
  <li>Georgia</li>
  <li>Lucida Sans, Lucida Grande, Lucida</li>
  <li>Palatino Linotype</li>
  <li>Tahoma</li>
  <li>Times New Roman ,Times</li>
  <li>Trebuchet</li>
  <li>Verdana</li>
</ul>

##网页中引入web font

最近网页安全字体的替代方案逐渐流行。现在可以将字体上传到服务器，然后使用CSS中的`@font-face`属性将其引入站点。这对在线排版有着非凡的意义。

```css
@font-face {
  font-family: 'Bryant Normal';
  src: url('bryant-normal.eot');
  src: url('bryant-normal.eot') format('embedded-opentype'),
       url('bryant-normal.woff') format('woff'),
       url('bryant-normal.ttf') format('truetype'),
       url('bryant-normal.svg') format('svg');
}
body {
  font-family: 'Bryant Normal', 'Helvetica Neue', Arial, Helvetica, sans-serif;
}
```

在此的一个小的缺陷是，在站点中使用任何字体从技术上来说可行，但并不意味着在法律上有权这么做。字体属于艺术作品，若将其放到你的服务器，则可能会被别人偷用。总之字体的使用都需要授权（license）的容许。

幸运的是，新字体的价值已经被认可，而且许多公司也以及开始开发授权的方式，依次来将字体引入网站。一些公司，例如[TypeKit](https://typekit.com/)和[Fontdeck](http://fontdeck.com/)采用订购方式来授权字体，而其他的，例如[Google Fonts](http://www.google.com/webfonts)则采用免费授权的方式。在上传任何字体之前请确保你这样做得到了必要的授权，如果尚未得到，你可以再上述的公司中寻求帮助来找到同样的字体或者合适的替代字体。

还有一个小的缺陷便是浏览器的支持。尽管`@font-face`属性出现已经有段时间了，但是老点的浏览器对其支持很差。现代的浏览器对其的支持则很是完美。幸运的是，我们可以使用新的字体，遇到不支持的则可降级到其他字体。这些在之前`font-family`属性中已经讨论。

##`cite`,`q`&`blockquote` 

在线写作可能会有作品名称或者引语（quotation）的引用。引语包括，对话（dialog），叙述性文字（prose），以及一些来源外部资源的引语。这些作品名或者引语在HTML中可以全部用`cite`,`q`&`blockquote`元素语义地包裹。

###作品名称的引用（`cite`元素）

HTML中`cite`元素用来标示作品名称的引用。`cite`元素和`cite`属性不应该混淆。`cite`元素为作品名称提供了一个富有语义化的语境，而`cite`属性则属于是引用资源的一种唯一标识符（URI）。`cite`元素中只用来表示作品名称的引用，不应该包裹引用资源的其他内容。作品则包括书籍，电影，歌曲，等等。对于外部引用，`cite`元素可以用来包含有相关性的超链接。

```html
<p><cite><a href="http://www.amazon.com/Steve-Jobs-Walter-Isaacson/dp/1451648537" title="Steve Jobs">Steve Jobs</a></cite> by Walter Isaacson is truly inspirational.</p>
```

<div class="code-box">
<h4>作品名引用的Demo</h4>
<p><cite><a href="http://www.amazon.com/Steve-Jobs-Walter-Isaacson/dp/1451648537" title="Steve Jobs">Steve Jobs</a></cite> by Walter Isaacson is truly inspirational.</p>
</div>

###`q`

一段文字中经常会有对话或者叙述性文字的引用。在这种情景下，行内元素`q`也就是所谓的引语就很适合使用。`q`元素应该用来语义化的表示对话或者叙述性的文本，而不用来标示其他类型的引用。

```html
<p>Steve Jobs once said, <q>“One home run is much better than two doubles.”</q></p>
```

##`cite`属性

`q`元素中一个可用的属性便是`cite`。`cite`属性以唯一标识符的形式标示了引语的引用。`cite`属性不会改变元素的视觉表现，它仅仅对屏幕阅读器或者其他设备有价值。因为`cite`属性在浏览器中不会有视觉的表现，如果可能推荐将引语的超链接作为它的值。

```html
<p><a href="http://www.businessweek.com/magazine/content/06_06/b3970001.htm" title="Steve Jobs' Magic Kingdom">Steve Jobs</a> once said, <q cite="http://www.businessweek.com/magazine/content/06_06/b3970001.htm">“One home run is much better than two doubles.”</q></p>
```

<div class="code-box">
<h4>引用Demo</h4>
<p><a href="http://www.businessweek.com/magazine/content/06_06/b3970001.htm" title="Steve Jobs' Magic Kingdom">Steve Jobs</a> once said, <q cite="http://www.businessweek.com/magazine/content/06_06/b3970001.htm">“One home run is much better than two doubles.”</q></p>
</div>

###附加引用（`blockquote`元素）

`blockquote`元素用来表示，来源于外部通常有多行的块级文本的引用。`blockquote`元素属于块级元素，它可能会在其中嵌套其他的块级元素，包括标题和段落。

```html
<blockquote>
  <p>“In most people’s vocabularies, design is a veneer. It’s interior decorating. It’s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.”</p>
  <p>— Steve Jobs in Fortune Magazine</p>
</blockquote>
```

###大段引语（External Quotation）中的来源声明（Citation）

`blockquote`元素中的大段引用通常需要声明其出处。这个声明或许很简单，例如，作者或者来源。当然它也可以包括更多的信息。

大段引用中可会同事包含`cite`属性和`cite`元素。就像上诉的`q`元素一样`blockquote`元素中可以包含`cite`元素。`cite`元素可以跟随在实际引语的后面，用来表示这段引用的来源。

`cite`元素和`cite`属性都只有纯粹的语义化意义，没有视觉上的变化，因此如果可能最好包含相关的超链接。这些超链接无论是作品的标题或者其他引用（作者、艺术家等）在其首次出现的时候都应该高亮显示。

```html
<blockquote cite="http://money.cnn.com/magazines/fortune/
fortune_archive/2000/01/24/272277/index.htm">
  <p>“In most people’s vocabularies, design is a veneer. It’s interior decorating. It’s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.”</p>
  <p>— <a href="http://en.wikipedia.org/wiki/Steve_Jobs" title="Steve Jobs">Steve Jobs</a> in <cite><a href="http://money.cnn.com/magazines/fortune/fortune_archive/2000/01/24/272277/index.htm" title="Apple's One-Dollar-a-Year Man">Fortune Magazine</a></cite></p>
</blockquote>
```

<div class="code-box">
<h4>大段引用Demo</h4>
<blockquote cite="http://money.cnn.com/magazines/fortune/
fortune_archive/2000/01/24/272277/index.htm">
  <p>“In most people’s vocabularies, design is a veneer. It’s interior decorating. It’s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.”</p>
  <p>— <a href="http://en.wikipedia.org/wiki/Steve_Jobs" title="Steve Jobs">Steve Jobs</a> in <cite><a href="http://money.cnn.com/magazines/fortune/fortune_archive/2000/01/24/272277/index.htm" title="Apple's One-Dollar-a-Year Man">Fortune Magazine</a></cite></p>
</blockquote>
</div>

<div class="code-box">
<h4>在	CSS中自动标记引用文本</h4>
<p>
与其在HTML中添加引用文本的表示，不如在CSS中让其自动完成。老的浏览器中英文语言的支持问题，在	CSS中实现这个有点羸弱，而现代浏览器对语言的越来越好的支持，实现自动化就越发的简单。
</p>
<p>
在	CSS中给引用文本自动添加引号，需要使用<code>before</code>和<code>after</code>伪元素。<code>before</code>和<code>after</code>伪元素使用<code>quotes</code> 和<code>content</code>属性在必要的时候动态添加引号。</p>
<p>

如下便是如何使用伪元素自动给<code>q</code>元素添加引号。对此深入了解可以查看 <a href="http://css-tricks.com/pseudo-element-roundup/">pseudo-elements</a>和<a href="http://css-tricks.com/pseudo-element-roundup/">how to use quotation marks</a>这两篇文章。
</p>
<div class="highlight"><pre><code class="html language-html" data-lang="html">q {
  quotes: '“' '”' '‘' '’';
}
q:before {
  content: '“';
  content: open-quote;
}
q:after {
  content: '”';
  content: close-quote;
}
</code></pre></div>
</div>

##资源
<ul class="col-2">
  <li><a href="http://dev.opera.com/articles/view/29-text-styling-with-css/" title="Text styling with CSS" rel="nofollow">Text styling with CSS</a> via Dev.Opera</li>
  <li><a href="http://html5doctor.com/blockquote-q-cite/" title="Quoting and citing with blockquote, q, cite, and the cite attribute" rel="nofollow">Quoting and citing with blockquote, q, cite, and the cite attribute</a> via HTML5 Doctor</li>
  <li><a href="http://www.impressivewebs.com/css-font-shorthand-property-cheat-sheet/" title="CSS Font Shorthand Property Cheat Sheet" rel="nofollow">CSS Font Shorthand Property Cheat Sheet</a> via Impressive Webs</li>
  <li><a href="http://www.amazon.com/Elements-Typographic-Style-Robert-Bringhurst/dp/0881791326" title="The Elements of Typographic Style" rel="nofollow">The Elements of Typographic Style</a> by Robert Bringhurst</li>
</ul>








