---
layout: post
title: 背景和渐变
categories: [html-css]
---

{{ page.title }}
================

<p class="meta">LESSON 5 · 2013/06/6</p>


背景是CSS中很重要的一部分，因为它可以让你很容易的改变一个元素的构成。背景可以用来装饰元素，也可以给元素内容提供一种视觉上下文环境，增加易用性。无论在网页中使用背景有多少，背景在整个网页设计中都有一个很重要的影响。

给一个元素添加背景可以总结为几种不同的方式。最常用的有，纯色，图片，或者两种的结合。能够精准的控制背景如何应用到元素，给整个界面提供了很好的方向。

在CSS3中，引入了新的[背景和能力](http://www.slideshare.net/maxdesign/css3-backgrounds)，包括支持渐变背景和在一个元素中使用多个图片作为背景，随着浏览器越来越广泛的支持，这也就扩展了现代网页设计的可能性。

##增加背景色

给元素添加背景最快的方式便是使用`background`或者`background-color`给元素添加单色背景。`background`属性接受颜色或者图片。`background-color`属性则只能用于背景颜色。这两个属性都可以起作用，选用那个则取决于你的偏好和实际情况。

```css
div {
  background: #f60;
  background-color: #f60;
}
```

背景颜色值的声明有几个可选方案，就像其他的颜色值一样，你可以选择关键词，十六进制颜色值，RGB，RGBa，HSL，HSLa。最常用的是十六进制的颜色值，但是RGBa，HSLa也值得注意，因为它们可以通过α通道来设置背景色的透明度。设置不透明度为30%的黑色则可以使用`rgba(0,0,0,0.3)`。容许透明度的背景则将网页设计提高了以全新的水平。RGBa，HSLa并没有得到全浏览器的支持，因此在CSS中为使用透明度的颜色提供一个降级色则显得尤为重要。

```css
div {
  background: #b2b2b2;
  background: rgba(0, 0, 0, 0.3);
}
```

##增加背景图片

除了能给元素设置背景色外，还能给元素设置背景图片。背景图片的工作方式和背景色相似，还有几个附加的属性来进一步设置背景图片。如之前所说的，你可以使用`background`属性或者`background-image`属性。无论你是用那个属性你都需要使用`url`值来声明图片源。`url`值里面设置图片的路径。

```css
div {
  background: url('alert.png');
  background-image: url('alert.png');
}
```

在背景图片中仅仅使用`url`值带来的结果可能不受欢迎，因为它默认将背景图片从元素内的左上角同时横向纵向铺满整个元素。当然此时我们就可以使用`background-repeat`和`background-position`来进一步调整。

###背景重复

背景图片在默认情况下会在横向和纵向方向无限重复，背景图片的重复可以在`background`属性`url`值后面或者使用`backgrond-repeat`属性设置。

```css
div {
  background: url('alert.png') no-repeat;
  background-image: url('alert.png');
  background-repeat: no-repeat;
}
```

背景重复的值接受四个值，`repeat` `repeat-x` `repeat-y` `no-repeat`。`repeat`值是默认值，它会让背景图片在横向和纵向方向重复平铺，`repeat-x`设置背景图片横向平铺，相应`repeat-y`则为纵向平铺。`no-repeat`如其字面意义一样，使背景图片只显示一次，不再重复平铺。

###背景位置

使用`background-position`属性可以设置背景图片在哪个地方显示或者从那个地方开始重复平铺。就像其他背景属性一样，背景位置也可以在`background`属性`url`值后面，或者单独使用`backgrond-position`属性。

```css
div {
  background: url('alert.png') 10px 10px no-repeat;
  background-image: url('alert.png');
  background-position: 10px 10px;
  background-repeat: no-repeat;
}
```

`background-position`属性需要两个值，横向偏移值（第一个值）和纵向偏移值（第二个值）。设置背景位置的值可以使用`top` `right` `bottom` `left`等关键词，像素值，百分数，或者其他尺寸值。关键词和百分数的工作方式比较相似。关键词`top` `left`等同于百分数`0` `0`， `right` `bottom`则等同于百分数`100%` `100%`。与关键词相比百分数还可以使用一个值`50%`将背景图片定为到元素的中间。定为背景图片到元素顶部居中可以使用`50%` `0`。像素值在此也经常使用，因为使用像素值可以很精准地定为背景图片。

![使用百分数和关键词定为背景图片][img-1]

<div class="code-box">
<h4>警告文字背景示例</h4>
<div>
<h5>HTML</h5>
<div class="highlight"><pre><code class="html language-html" data-lang="html"><span class="nt">&lt;p&gt;&lt;strong&gt;</span>Warning!<span class="nt">&lt;/strong&gt;</span> You are walking on thin ice.<span class="nt">&lt;/p&gt;</span>
</code></pre></div>
<h5>CSS</h5>
<div class="highlight"><pre><code class="css language-css" data-lang="css"><span class="nt">p</span> <span class="p">{</span>
  <span class="k">background</span><span class="o">:</span> <span class="m">#fff6cc</span> <span class="sx">url('warning.png')</span> <span class="m">15px</span> <span class="m">50</span><span class="o">%</span> <span class="k">no-repeat</span><span class="p">;</span>
  <span class="k">border</span><span class="o">-</span><span class="n">radius</span><span class="o">:</span> <span class="m">6px</span><span class="p">;</span>
  <span class="k">border</span><span class="o">:</span> <span class="m">1px</span> <span class="k">solid</span> <span class="m">#ffd100</span><span class="p">;</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#000</span><span class="p">;</span>
  <span class="k">padding</span><span class="o">:</span> <span class="m">10px</span> <span class="m">10px</span> <span class="m">10px</span> <span class="m">38px</span><span class="p">;</span>
<span class="p">}</span>
</code></pre></div>
</div>
<div class="code-box-alertbg">
<h5>Demo</h5>
<p><strong>Warning!</strong> You are walking on thin ice.</p>
</div>
</div>

##CSS3渐变背景

在CSS3中引入了渐变背景，一经引入便在设计师和开发者中得到了极大的推崇。尽管渐变背景并不是每个浏览器都支持，但在所有现代浏览器中却得到了很好的支持。


可以将渐变背景当做背景图片。可以像背景图片中一样使用`background`或者`background-image`来创建渐变背景。而属性的值的根据渐变类型不同（线性和径线）而略有不同。

<div class="code-box">
<h4>浏览器特有属性值(浏览器私有前缀)</h4>
<p>在浏览器对CSS3不同特性功能缓慢支持的过程中，每个浏览器对新属性的支持有个略微的不同，因此浏览器都使用了私有前缀来分别标示。渐变背景自然首当其冲，每个浏览器对渐变背景都有各自倾向的呈现方式。幸运的是，大部分的浏览器都基于标准，当然在代码中最好对齐全部支持。</p>
<p>当然随着对CSS3支持的日益完美，浏览器逐渐开始支持标准的写法，私有前缀也越来越不重要，当然最好还是在代码中全部使用以此来兼容老点的浏览器。</p>
<ul>
<li>火狐浏览器：<code>-moz-</code></li>
<li>Webkit内核浏览器（Chrome & Safari）：<code>-webkit-</code></li>
<li>微软IE浏览器：<code>-ms-</code></li>
<li>Opera浏览器：<code>-o-</code></li>
</ul>
</div>

###线性渐变背景

在此之前设计师和开发者一直裁剪图片来作为渐变背景，这行得通，只是这样费时又难以更换。幸运的是这样的日子就要过去了，现在可以通过CSS来实现线性渐变背景。如果渐变色需要改变，再也不用重新裁剪图片然后上传到服务器这么麻烦了，只需简单的改变CSS值即可达到目的。这确实很棒！

```css
div {
  background: #70bf32;
  background: url('linear-gradient.png') 0 0 repeat-x;
  background: -webkit-linear-gradient(#a1e048, #6a942f);
  background:    -moz-linear-gradient(#a1e048, #6a942f);
  background:     -ms-linear-gradient(#a1e048, #6a942f);
  background:      -o-linear-gradient(#a1e048, #6a942f);
  background:         linear-gradient(#a1e048, #6a942f);
}
```

<p class="post5-demo-1">Linear Gradient Background</p>

以上便是覆盖所有浏览器私有前缀的写法。你也可以看得到`linear-gradient(#a1e048, #6a942f)`的标准写法已经得到了大多数浏览器的支持，因此之后，包括径向渐变，我们只写标准的写法，但是不要在个人项目中忘记其他的兼容值。

线性渐变默认从元素的顶部（top）渐变到底部（bottom）。在颜色值之前使用关键词或者角度值即可改变渐变方向。例如，使用`to right`即可使渐变从左往右进行。当然，也可以混合使用方向关键词，譬如，你想要从左上角渐变到右下角，使用`to bottom right`即可。

```css
div {
  background: linear-gradient(to bottom right, #a1e048, #6a942f);
}
```

当使用倾斜的线性渐变的时候，渐变并不是从元素的一角渐变至另一角，而是它会首先确定元素的绝对中心，然后在垂直角也就是渐变应该开始的地方放置一个锚点，然后朝着渐变值内定义的角度绘制渐变。因为这些渐变的起始角并不固定因此称之为“magic corners”，[Eric Meyer的文章中对线性渐变值内的方向值做了很好的研究](http://meyerweb.com/eric/thoughts/2012/04/26/lineargradient-keywords/)，另外规范网站[W3](http://dev.w3.org/csswg/css-images-3/#gradients)中对带角度渐变的配图（下图）也可很好的解释（译者注）。

![带角度的线性渐变][img-2]

除关键词之外，角度值也可以使用。如果你想要渐变从左上角（`left top`）你可以使用角度值`315deg`。

<div  class="code-box">
	<h3>旧渐变语法中关键词的写法</h3>
	<p>在之前老的线性渐变语法中关键词的写法中不需要关键词<code>to</code>，相反关键词定义的是渐变的起始角。因此上面倾斜渐变的代码中老的写法则是<code>top left</code>而不是<code>to bottom right</code>。</p>
	<p>新的语法得到了一些浏览器的支持，若你的新写法在你浏览器中不被支持，你或许可以试试旧的写法，总之记住随着浏览器更新新的语法终究会被支持。</p>
</div>


###径向渐变

线性渐变广泛使用的同时，也会有径向渐变的需求。径向渐变工作方式很像线性渐变，两者的值也大部分通用。然而径向渐变中位置、尺寸、渐变半径的值则有点复杂，我们在此只暂时基本的用法，[也可以在此对径向渐变进行深入了解](http://dev.opera.com/articles/view/css3-radial-gradients/)。

```css
div {
  background: #70bf32;
  background: url('radial-gradient.png') 50% 50% no-repeat;
  background: radial-gradient(#a1e048, #6a942f);
}
```

<p class="post5-demo-2">Radial Gradient Background</p>

<div class="code-box">
<h3>CSS3渐变生成器</h3>
<p>完全手动书写CSS3渐变代码确实是个挑战，特别是对于新手。幸运的是，一些<a href="http://ie.microsoft.com/testdrive/graphics/cssgradientbackgroundmaker/default.html">CSS3渐变生成器</a>应需而生，不同的渐变生成器都有细微的差别，一些提供调整和示例，另外的会提供一些可选的列表。如果需要这些工具的帮助，我在此建议对齐多做些研究来找到合适的。</p>
</div>

[img-1]:http://learn.hicc.me/images/2013/06/background-percentages.png


[img-2]:http://static.9ikblog.com/blog/2012/11/gradient-diagram.png





