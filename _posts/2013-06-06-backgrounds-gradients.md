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