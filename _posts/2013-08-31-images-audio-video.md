---
layout: post
title: 图片、音频和视频
categories: [html-css]
---

{{ page.title }}
================

<p class="meta">LESSON 7 · 2013/08/31</p>

英文原文：[Images, Audio, & Video](http://learn.shayhowe.com/html-css/images-audio-video)


用户在冲浪搜索感兴趣内容的时候，都是以纯文本的形式出现的，为了丰富文本，HTML也给用户提供了用图片，音频和视频组成的富媒体。

网站能够包含图片，音频和视频已经有段时间了，浏览器对图片的支持确认不错，但是对音频和视频和支持却差强人意。随着新技术的兴起，设计媒体的推动，越来越的音轨和视频剪辑以它们各自的方式出现在网上。

今天，我们能够自由的使用图片，音频和视频是通过浏览器中HTML5或者flash来实现的。

##添加图片

要[添加图片](http://dev.opera.com/articles/view/17-images-in-html/)需要使用`img`这个内联元素。`img`元素是自闭合的，不需要包裹其他内容，只有单个标签。`img`属性要起作用还需要`src`属性来指定所需的图片源。`src`属性的值是URL，通常情况下相对于网页地址。

结合`src`属性使用的是称之为替代文本的`alt`属性，在`img`元素应该使用`alt`属性，在图片无法显示的时候，`alt`属性值就会显示，而且在鼠标移到图片上`alt`属性通常还会以提示性文本提示。


```html
<img src="cows.jpg" alt="Brown and white cows in a field">
```

<div class="code-box">
<h4>添加图片Demo</h4>
<div>
<img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field">
</div>
</div>

<div class="code-box">
<h4>所支持的图片格式</h4>
<p>
图片的有很多的格式，每个浏览器对这些的支持不尽相同。大体上来说，都支持的格式包括<code>bmp</code>，<code>gif</code>，<code>jpg</code>和<code>png</code>，使用最广泛的有<code>jpg</code>和<code>png</code>。<code>jpg</code>能够在较小尺寸，较快加载速度的情况下保持更高的的色彩数，<code>png</code>格式则用来显示透明图片或者低色彩数的图片。
</p>
</div>