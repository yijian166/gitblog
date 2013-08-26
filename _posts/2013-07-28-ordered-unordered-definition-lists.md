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
</div>

</div>

##定义列表





