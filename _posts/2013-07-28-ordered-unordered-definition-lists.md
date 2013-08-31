---
layout: post
title: 无序列表，有序列表和定义列表
categories: [html-css]
---

{{ page.title }}
================

<p class="meta">LESSON 5 · 2013/07/28</p>

英文原文：[Unordered, Ordered, & Definition Lists](http://learn.shayhowe.com/html-css/ordered-unordered-definition-lists)

列表在日常生活中不可或缺。To-do列表决定了需要完成的事情。导航提供了每步怎么走的方向列表。食谱则提供了各个步骤已经所需成分。列表无处不在，这也就是列表为什么在网上同样流行。

在构建一个页面的时候HTML中提供了三种类型的列表，包括，无序列表，有序列表和定义列表。无序列表用来表示序号不重要的列表，有序列表则用来表示序号相对比较重要的列表。而其他的譬如说有一个术语列表和其描述，或许在这种情况下对于一个词汇表来说定义列表是最好的选择。选择使用那种类型的列表，或者只使用一种列表，都取决于要展示的内容，以及哪种列表能够以最语义的方式展示内容。

HTML中[三个不同类型的列表](http://dev.opera.com/articles/view/16-html-lists/)在CSS中可以赋予很多种的样式。其中包括决定列表前显示那种类型的符号，这些符号包括方形，原型，数字，阿拉伯字母，或者甚至让其不显示，同样也可以在样式中决定列表是垂直还是横向显示。

##无序列表

无序列表只是纯粹的表示一些相关项的列表，这些项或者顺序不重要或者没有编号或者不以字母顺序为序。在HTML中创建无序列表使用块级元素`ul`，列表中的项用块级元素`li`表示。

默认情况下大多数的浏览器会在每个无序列表项的前面加上一个实心的圆点。这些实心的圆点代表了列表的项并且可以用CSS来更改

```html
<ul>
  <li>iPad</li>
  <li>iPhone</li>
  <li>MacBook Air</li>
</ul>
```

<div class="code-box">
<h4>无序列表Demo</h4>
<div>
<ul>
  <li>iPad</li>
  <li>iPhone</li>
  <li>MacBook Air</li>
</ul>
</div>

</div>

##有序列表

有序列表元素`ol`，以及其中的列表项和无序列表相似。主要的不同在于有序列表中每项的顺序很重要。与无序列表显示一个实心的小圆点不同，默认有序列表显示数字的序号。使用CSS可以将其更改为字母、罗马数字或者其他。

```html
<ol>
  <li>iPad</li>
  <li>iPhone</li>
  <li>MacBook Air</li>
</ol>
```


<div class="code-box">
<h4>有序列表Demo</h4>
<div>
</div>
<ol>
  <li>iPad</li>
  <li>iPhone</li>
  <li>MacBook Air</li>
</ol>
</div>

随着HTML5的引入，有序列表`ol`中新增了两个属性`start`和`reversed`。`start`设置了有序列表从什么时候起始。默认情况下，有序列表从1开始。当然你可能需要从5开始的有序列表，你只需设置`start`属性的值为`5`即可。需要注意的是，你可能在有序列表中使用其他类型的顺序，但是`start`只支持整数值。

```html
<ol start="30">
  <li>iPad</li>
  <li>iPhone</li>
  <li>MacBook Air</li>
</ol>
```
<div class="code-box">
<h4><code>start</code>属性Demo</h4>
<div>
<ol start="30">
  <li>iPad</li>
  <li>iPhone</li>
  <li>MacBook Air</li>
</ol>
</div>

</div>

`reversed`属性则容许你倒序排列有序列表。五个项的有序列表从1到5排序也可以倒序排列从5到1.`reversed`属性属于布尔顺序，因此它不接受任何值。只需在`ol`起始标签中包含即可，因为`start`和`reversed`属性属于HTML5中才有的属性，因此可能并未得到所有浏览器的支持。

另外，在有序列表中可以使用`value`属性来更改单个项的序号。设置了`value`值项之后的项的需要将根据`value`值来重新排序。例如，如下第二个项`value`设置为`9`，改项的序号则被认为是第九，其后的项就从10开始排序。

```html
<ol>
  <li>iPad</li>
  <li value="9">iPhone</li>
  <li>MacBook Air</li>
</ol>
```
<div class="code-box">
<h4><code>value</code>属性Demo</h4>
<div>
<ol>
  <li>iPad</li>
  <li value="9">iPhone</li>
  <li>MacBook Air</li>
</ol>
</div>

</div>

##定义列表

在网络上通常还可以看到另外一种列表，有别于无序列表和有序列表，它便是定义列表。定义列表通常用来概述多个及其描述，通常是专业集。在HTML中使用`dl`元素来表示定义列表，定义列表中不使用`li`定义列表项，而需要使用两个元素：定义术语用`dt`元素，定义属于的描述用`dd`元素。

一个定义列表可能会有多个定义和描述，一个接一个。另外一个定义列表，可能每个描述对应多个术语，也可能每个术语有多个描述。单个的属于可能有多个意思，根据多个定义。相比之前，一个描述更可能适合多个术语。

在添加定义术语和描述时，属于必须在描述之前。随后的术语和描述依此排列即可。

定义列表中没有任何的列表项元素，然而定义列表中默认会将描述缩进。你可以通过CSS的`margin`和`padding`属性来调整缩进。

```html
<dl>
  <dt>study</dt>
  <dd>the devotion of time and attention to acquiring knowledge on an academic subject, esp. by means of books</dd>
  <dt>design</dt>
  <dd>a plan or drawing produced to show the look and function or workings of a building, garment, or other object before it is built or made</dd>
  <dd>purpose, planning, or intention that exists or is thought to exist behind an action, fact, or material object</dd>
  <dt>business</dt>
  <dt>work</dt>
  <dd>a person’s regular occupation, profession, or trade</dd>
</dl>
```

<div class="code-box">
<h4>定义列表Demo</h4>
<div>
<dl>
  <dt>study</dt>
  <dd>the devotion of time and attention to acquiring knowledge on an academic subject, esp. by means of books</dd>
  <dt>design</dt>
  <dd>a plan or drawing produced to show the look and function or workings of a building, garment, or other object before it is built or made</dd>
  <dd>purpose, planning, or intention that exists or is thought to exist behind an action, fact, or material object</dd>
  <dt>business</dt>
  <dt>work</dt>
  <dd>a person’s regular occupation, profession, or trade</dd>
</dl>
</div>
</div>


##列表嵌套

HTML中列表之所以强大的原因是，列表间容许嵌套。无序列表可以嵌套在有序列表或者定义列表，定义列表也可以定义在无序列表和有序列表中，反之亦然。每种列表都可以重复嵌套在其他的列表中。当然列表的这种能力并不是让整个页面都定义在列表中。使用列表仍然需要保证其最大的语义性。

嵌套列表很是容易。决定在哪里嵌套后，先不要闭合这个列表标签，插入需要嵌套的列表之后在闭合列表元素，然后继续原来的列表。

```html
<ol>
  <li>Walk the dog</li>
  <li>Fold laundry</li>
  <li>Go to the grocery and buy:
    <ul>
      <li>Milk</li>
      <li>Bread</li>
      <li>Cheese</li>
    </ul>
  </li>
  <li>Mow the lawn</li>
  <li>Make dinner</li>
</ol>
```

<div class="code-box">
<h4>嵌套列表Demo</h4>
<div >
<ol>
  <li>Walk the dog</li>
  <li>Fold laundry</li>
  <li>Go to the grocery and buy:
    <ul>
      <li>Milk</li>
      <li>Bread</li>
      <li>Cheese</li>
    </ul>
  </li>
  <li>Mow the lawn</li>
  <li>Make dinner</li>
</ol>
</div>
</div>

##列表项格式化

无序列表和有序列表默认会和列表项一起出现。对无需列表来说列表项的前面默认是实心的圆点而有序列表中则是数字。[使用CSS](http://coding.smashingmagazine.com/2009/12/11/styling-html-lists-with-css-techniques-and-resources/)列表项目的内容和位置都可以调整。

###列表样式类型属性

列表样式类型，`list-style-type`属性可以用来设置列表项的内容和样式。[可用的值](https://developer.mozilla.org/en/CSS/list-style-type)，从正方形，十进制数字编号，到亚美尼亚编号。这些属性值都也可以用在无序和有序列表。也就是说有可能给无序列表使用数字编号，或者相反。这样做是不推荐的，因此这样就违背了选用元素的初衷，当然也违背了语义化的原则。

列表样式可以用到所有的列表项或者单个的，这都取决于CSS的设置。很少需要为单个的列表项使用单独的不同的样式，当然样式上可以这么做。

<div class="code-box">
  <h4>列表样式类型属性的值</h4>
  <div class="post6-list-1">
  <ul class="col-2">
    <li><code>none</code> No list item</li>
    <li><code>disc</code> A filled circle</li>
    <li><code>circle</code> A hollow circle</li>
    <li><code>square</code> A filled square</li>
    <li><code>decimal</code> Decimal numbers</li>
    <li><code>decimal-leading-zero</code> Decimal numbers padded by initial zeros</li>
    <li><code>lower-roman</code> Lowercase roman numerals</li>
    <li><code>upper-roman</code> Uppercase roman numerals</li>
    <li><code>lower-greek</code> Lowercase classical Greek</li>
    <li><code>lower-alpha / lower-latin</code> Lowercase ASCII letters</li>
    <li><code>upper-alpha / upper-latin</code> Uppercase ASCII letters</li>
    <li><code>armenian</code> Traditional Armenian numbering</li>
    <li><code>georgian</code> Traditional Georgian numbering</li>
  </ul>
  </div>
</div>

```css
ul {
  list-style-type: circle;
}
```

<div class="code-box">
<h4>列表样式Demo</h4>
<div class="post6-list-2">
<ul>
    <li>iPad</li>
    <li>iPhone</li>
    <li>MacBook Air</li>
  </ul>
</div>
</div>

###在列表项前使用图片

在多数情况下默认的列表样式不够用，或者你仅仅想要自定义你的列表样式。改变列表的样式完全是可能的，有几个可行的方案。

原始的方法是使用`list-style-image`属性，在其值中传一个图片的URL地址即可改变样式。尽管这个方法可以工作，却不是最好的方案。一个更好的方案是在列表项中结合背景图片和一定的padding值。

给列表项目设置背景图片，移出默认的`list-sytle`属性，在左边设置一定的`padding`值，来给背景图片提供空间，与使用`list-style-image`属性不同的是，此方案可以控制定位，容许使用雪碧图（sprites），以及其他优势。

```css
li {
  background: url('tick.png') 0 0 no-repeat;
  list-style: none;
  padding-left: 20px;
}
```

<div class="code-box">
<h4>在列表项中使用图片Demo</h4>
<div class="post6-list-3">
<ul>
    <li>iPad</li>
    <li>iPhone</li>
    <li>MacBook Air</li>
  </ul>
</div>
</div>

<div class="code-box">
<h4>在列表项样式中使用字符</h4>
<p>对于支持<code>:before</code>伪元素的浏览器，可以在<code>content</code>属性中传入一个十六进制的转义字符作为列表项目的样式。首先，设置<code>list-style</code>属性为<code>none</code>来移出列表项的默认样，然后在<code>:before</code>使用<code>content</code>属性，<code>content</code>属性的值使用十六进制的转义字符。最后添加右边的<code>margin</code>值来为此提供空间。</p>
<p>Mark Newhouse在之前写了一篇文章分别讨论了这种技术和其他不同的<a href="http://www.alistapart.com/articles/taminglists/" title="CSS Design: Taming Lists" rel="nofollow">taming lists（列表优化）</a>技术。</p>
<div >

</div>
<h5>Demo</h5>
<div class="post6-list-4">
<ul>
    <li>iPad</li>
    <li>iPhone</li>
    <li>MacBook Air</li>
  </ul>
</div>


</div>

```css
li {
  list-style: none;
}
li:before {
  content: "\2708";
  margin-right: 6px;
}
```

###列表样式位置属性

默认情况下列表项的样式标志（例如小圆点）都是在列表项元素的内部，内容的左边，这种列表样式的位置为`outside`，意思是，所有的内容都显示在列表样式的左边。使用`list-style-position`属性我们可以将默认值`outside`改为`inside`或者`inherit`。

`outside`和`inside`的不同在于，`outside`是元素内容显示在列表样式的左边，并且不容许内容包裹，而`inside`值则在第一行使得内容处于列表样式的左边，而容许其他行的内容包裹。

```css
ul {
  list-style-position: inside;
}
```

<div class="code-box">
<h4></h4>
<div class=“post6-list-5”>
<ul>
    <li>iPad – iPad is a magical window where nothing comes between you and what you love. Now that experience is even more incredible with the new iPad.</li>
    <li>iPhone – The faster dual-core A5 chip. The 8MP camera with all-new optics also shoots 1080p HD video. And introducing Siri. It’s the most amazing iPhone yet.</li>
    <li>MacBook Air – The new MacBook Air is faster and more powerful than before, yet it’s still incredibly thin and light. It’s everything a notebook should be. And more.</li>
  </ul>
</div>
</div>

##列表样式属性的简写模式

在上述讨论的列表样式属性都在合并简写在`list-style`属性中，使用`list-style`属性，可以有一个或者三个值。其值的顺序从`list-style-type`到`list-style-position`到`list-style-image`。

```css
ul {
  list-style: circle inside;
}
ol {
  list-style: outside;
}
```

##列表水平显示

偶然也需要水平而不是垂直显示列表，或许你想使列表变成多列，创建一个导航列表，或者仅仅是只有几个列表项想要单行显示。根据其内容和所期望的结果，在此有几个方法来让列表显示一行，包括内联显示和浮动显示。

###内联显示列表

让列表水平显示的最快方法是设置列表项`display`属性为`inline`。将列表项元素默认的块级改为内联级别。改变了`display`级别则容许列表项水平挨个排列。

设置列表项`display`属性为`inline`之后，列表项默认的样式（圆点、数字）就没有了。另外，每个列表项之间仅隔着一个空格的距离。因此，最好使用`margin`，`padding`属性来增加它们的间距。

```css
li {
  display: inline;
  margin: 0 10px;
}
```

<div class="code-box">
<h4></h4>
<div class="post6-list-6">
<ul>
    <li>iPad</li>
    <li>iPhone</li>
    <li>MacBook Air</li>
  </ul>
</div>
</div>

###浮动列表

改变列表项的`display`属性很迅速，但是这种方案并不能提供一个更为强大的控制，而且移除了列表默认的样式。如果列表样式是需要的，标示样式与内容间需要一定的宽度，或者想要更强大的控制，让列表浮动的方案要比改变列表`display`属性的方案要好。

设置列表项的`float`属性为`left`，将会使列表项一个接一个的没有空隙的紧靠。另外列表项的`display`属性仍是默认的。为了不让浮动显示的列表揉杂到一起`margin`，`padding`属性同样需要设置。

浮动列表自身认识块级元素，容许了更大的控制，但是浮动同样破坏了页面的正常流。永远记得在浮动列表之后清除浮动，让页面回到正常的文档流。

```css
li {
  float: left;
  margin: 0 20px;
}
```

<div class=“code-box”>
<h4>浮动列表Demo</h4>
<div class="post6-list-7">
<ul class="group">
    <li>iPad</li>
    <li>iPhone</li>
    <li>MacBook Air</li>
  </ul>
</div>
</div>


```html
<ul>
  <li><a href="#" title="Profile">Profile</a></li>
  <li><a href="#" title="Settings">Settings</a></li>
  <li><a href="#" title="Notifications">Notifications</a></li>
  <li><a href="#" title="Logout">Logout</a></li>
</ul>
```

```css
ul {
  list-style: none;
  margin: 0;
}
li {
  float: left;
}
a {
  background: #404853;
  background: linear-gradient(#687587, #404853);
  border-left: 1px solid rgba(0, 0, 0, 0.2);
  border-right: 1px solid rgba(255, 255, 255, 0.1);
  color: #fff;
  display: block;
  font-size: 11px;
  font-weight: bold;
  padding: 0 20px;
  line-height: 38px;
  text-shadow: 0 -1px 0 rgba(0, 0, 0, 0.6);
  text-transform: uppercase;
}
a:hover {
  background: #454d59;
  box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.4);
  border-right: 1px solid rgba(0, 0, 0, 0.2);
  color: #d0d2d5;
}
li:first-child a {
  border-left: none;
  border-radius: 4px 0 0 4px;
}
li:last-child a {
  border-right: none;
  border-radius: 0 4px 4px 0;
}
```

<div class=“code-box”>
<h4>浮动列表Demo</h4>
<h5>HTML</h5>
<h5>CSS</h5>
<h5>Demo</h5>
<div class="post6-list-8">
<ul >
    <li><a href="#" title="Profile" rel="nofollow">Profile</a></li>
    <li><a href="#" title="Settings" rel="nofollow">Settings</a></li>
    <li><a href="#" title="Notifications" rel="nofollow">Notifications</a></li>
    <li><a href="#" title="Logout" rel="nofollow">Logout</a></li>
  </ul>
</div>
</div>





