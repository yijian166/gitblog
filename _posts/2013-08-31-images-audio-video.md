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

##改变图片尺寸

有几种方法可以改变图片尺寸，来适配网页。其中的一个选择是直接改变HTML中`img`标签的`height`和`width`属性，这样可以行得通，但却将样式放入了HTML中。因为样式都应该单独写到CSS文件中，我们使用CSS中的`height`和`width`属性。

指定图片的`height`和`width`值中其一个，另一个值会根据图片的长宽比自动调整。例如，如果我需要设置图片的高度为200px，但是不知道它的宽度是多少，我只需设置`height`为`200px`，图片的`width`就会自动按比例调整。当然也可以同时设置图片的`height`和`width`属性，但是这样可能会导致图片扭曲。

在你对HTML、CSS中改变图片尺寸兴奋之前，想要告诫的是，如果可能最好是按照图片默认的大小渲染，1000ox的图片在浏览器中缩放到100px，意味着原始的1000px图片需要全部加载，然后再缩小，这不是一个理想的方案，会引起长时间的加载时间，特别是在移动设备上。

```css
img {
  height: 200px;
  width: 200px;
}
```

<div class="code-box">
<h4>改变图片尺寸Demo</h4>
<div class="post7-img">

<img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field">

</div>
</div>

##图片定位

图片可以按照多种方式定位，包括，内联、块级、左对齐，右对齐，等。所有的这些定为都是通过CSS中的`float`属性，以及其他的盒模型属性包括`margin`，`padding`，`border`和`display`。

###内联定位图片

`img`元素默认属于内联级别的元素，无需添加其他样式，将图片元素放入页面，其他内容将在必要的情况下与图片一块内联显示，如下例。

```html
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis  nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute <img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field">irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
```

<div class="code-box">
<h4>内联定位图片Demo</h4>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis  nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute <img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field">irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
</div>

在网页中让图片默认内联显示并不常见。大多让图片块级显示，或者浮动对齐显示。只有在图片有实际的意义并且有替代文本的时候，小图片才可以和文本一起内联显示。如果，一个图片，或者图标（icon），在页面中用来作为装饰，那么它应该在CSS中使用背景图片来显示。

###块级定位图片

在CSS中设置图片的`display`属性值为`block`将强制图片块级显示，这样，图片就会单独一行显示，环绕的文本在其上面或者下面显示。

```css
img {
  display: block;
}
```

<div class="code-box">
<h4>块级定位图片Demo</h4>
<div class="post7-img-1">
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis  nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute <img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field">irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
</div>
</div>

###左对齐或者右对齐定为图片

有时候，让图片按照内联（`inline`）或者块级（`block`）显示并不是一个好的用法。你可能想要图片左对齐，或者右对齐显示，让内容在必要的情况下环绕图片显示。要做到这样，你只需，设置CSS中`float`属性为`left`或者`right`。

浮动图片之后，其他的所有内容就会紧贴着环绕显示。为了提供一个充足额控件，还需要设置图片的`margin`属性。另外，如果你想，还可以使用`padding`，`border`，`background` 来给构建个框。

```css
img {
  background: #e8eae9;
  border: 1px solid #c6c9cc;
  float: right;
  margin: 8px 0 0 20px;
  padding: 4px;
}
```

<div class="code-box">
<h4>浮动图片Demo<h4>
<div class="post7-img-2">
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis  nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute <img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field"> irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
<p>Mauris ut lectus quis mauris ornare iaculis a vel ligula. Quisque sed est sed arcu tincidunt aliquet. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam posuere accumsan mauris, nec lacinia risus pretium et. Suspendisse eget nisi facilisis nisl tristique consequat. Vivamus scelerisque accumsan vulputate. Sed bibendum felis id dui ornare tincidunt. Sed a pretium nisl.</p>
</div>
</div>



