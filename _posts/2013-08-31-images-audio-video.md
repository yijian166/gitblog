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
<h4>浮动图片Demo</h4>
<div class="post7-img-2">
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis  nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute <img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field"> irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
<p>Mauris ut lectus quis mauris ornare iaculis a vel ligula. Quisque sed est sed arcu tincidunt aliquet. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam posuere accumsan mauris, nec lacinia risus pretium et. Suspendisse eget nisi facilisis nisl tristique consequat. Vivamus scelerisque accumsan vulputate. Sed bibendum felis id dui ornare tincidunt. Sed a pretium nisl.</p>
</div>
</div>


##增加音频

HTML5中新增了快速而简单的方式在网站上附加[音频和视频](https://developer.mozilla.org/en/Using_HTML5_audio_and_video)文件播放。使用`audio`[元素](https://developer.mozilla.org/En/HTML/Element/Audio)在网页上添加音频片段。就像`img`元素一样，`audio`元素也需要通过`src`属性来指定音频文件的URL。

```html
<audio src="images-audio-video/jazz.ogg"></audio>
```

在`audio`元素中，与`src`属性一起使用的还有其他一些属性，最常用的有`autoplay`，`controls`，`loop`和`preload`。


默认情况下，`audio`元素不会显示在页面上。如果设置了布尔属性`autoplay`，`audio`元素仍然不会显示在页面上，然而音频片段会在页面加载的时候自动播放。作为一个布尔型的值，`autoplay`属性就像一个开关一样（toggole function），它控制了音频在页面加载时播放与否。

在页面中真正显示`audio`元素，使用布尔型的`controls`属性，`controls`属性将会显示浏览器默认的控制栏包括，播放和暂停，进度条和音量。

```html
<audio src="images-audio-video/jazz.ogg" controls></audio>
```

<div class="code-box">
<h4>添加音频Demo</h4>
<audio controls="">
    <source src="http://learn.hicc.me/images/2013/10/jazz.ogg" type="audio/ogg">
    <source src="http://learn.hicc.me/images/2013/10/jazz.mp3" type="audio/mpeg">
  </audio>
</div>


`audio`元素中的`loop`属性也是一个布尔型的属性，增加`loop`属性将会不断的重复音频。

最后，`preload`属性有三个不同的值，包括`none`，`auto`和`metadata`。`none`值，设置了不预先加载任何信息或者关于音频片段的任何数据，`auto`值则会预先加载所有的信息和数据。`metadata`值则会预先加载音频片段的媒体信息，譬如长度。当用户不是真正的需要或者想要听到声音的时候`preload`属性非常有用。它有助于节省宽带以及不加载不重要的音频片段来快速加载页面。

###音频预设（备选方案）

不同的浏览器可能支持不同格式的音频文件，也可能完全不支持`audio`元素。在此我们可以列出不同的备选方案，包括音频文件的不同格式，备用Flash，或者直接下载音频文件。

首先，使用`audio`元素我们可以通过`source`元素使用**多重来源（multiple sources）**指定不同的文件格式。`source`元素连同`src`属性和`type`属性一块工作。`src`属性指定了文件的URL，`src`属性则指定了音频片段的[MIME-type](http://en.wikipedia.org/wiki/Internet_media_type)，因此来帮助浏览器更好的理解音频文件的格式。

一些浏览器完全不支持HTML5中的`audio`元素，这种情况下，**Flash播放器**的备选方案就排上用场了。有很多的Flash播放器你需要研究那个最适合你。两个比较流行的可选方案包括[SWFObject](http://code.google.com/p/swfobject/)和[Flowplayer](http://flowplayer.org/)。

```html
<audio controls>
  <source src="jazz.ogg" type="audio/ogg">
  <source src="jazz.mp3" type="audio/mpeg">
  <object type="application/x-shockwave-flash" data="player.swf?audio=jazz.mp3">
    <param name="movie" value="player.swf?audio=jazz.mp3">
    <p>This browser does not support the audio format. Please <a href="jazz.mp3" title="Jazz song">download</a> the audio clip.</p>
  </object>
</audio>
```

为了覆盖到全部的浏览器，包括不支持`ogg`和`mp3`格式也没有安装Flash插件的浏览器，可以包含一个下载音频片段文件的链接。这个链接放置在Flash播放器代码内，作为最后的备选方案。

##添加视频

添加加[HTML5 视频](http://dev.opera.com/articles/view/introduction-html5-video/)和添加音频很相似，只是需要将`audio`元素替换成`video`元素。所有相同的属性（`source`，`autoplay`，`controls`，`loop`和`preload`）和预设备选方案也同样适用。

在`audio`中，如果`controls`属性没有设置，音频片段将不会显示。在视频中，不指定`controls`属性，视频也会显示出来，但是不会提供任何方式去播放视频，除非同时设置了`autoplay`属性。除非你有很好的理由不让用户开始，停止，和重播视频，你最好是包含`controls`属性。

因为视频将会在网页上显示，不妨给它指定尺寸，最常用的是在CSS中设置固定的`height`和`with`。这也有助于确保视频不至于太大，能够放入页面相应的不居中。另外，指定视频的尺寸也有助于浏览器更快的渲染视频，并且以此让浏览器分配给视频合适的空间。

```html
<video src="earth.ogv" controls></video>
```

<div class="code-box">
<h4>添加视频Demo</h4>
<video controls="">
    <source src="http://learn.hicc.me/images/2013/10/earth.mp4" type="video/mp4">
    <source src="http://learn.hicc.me/images/2013/10/earth.ogv" type="video/ogg">
  </video>
</div>



<div class="code-box">
<h4>自定义音频和视频控制栏</h4>
<p>默认情况下<code>audio</code>和<code>video</code>的控制栏由每个浏览器独立确定。根据网站或许需要<a href="http://www.netmagazine.com/tutorials/add-html5-video-your-site">自定义控制栏</a>，这可以实现，但是还需要一点JavaScript才能让播放器工作。</p>
</div>

###封面属性

`video`元素还有个可用的属性就是`poster`属性。`poster`属性容许以URL的形式定义一张图片，在视频播放之前显示。`poster`图片（封面图片）可以是来自视频的一帧禁止的图片，也可以是其他设计过的图片。正如，下面例子中使用牛的图片作为地球视频的封面。

```html
<video src="earth.ogv" controls poster="cows.jpg"></video>
```

<div class="code-box">
<h4>视频封面Demo</h4>
<video controls="" poster="http://learn.hicc.me/images/2013/09/cows.jpg">
    <source src="http://learn.hicc.me/images/2013/10/earth.mp4" type="video/mp4">
    <source src="http://learn.hicc.me/images/2013/10/earth.ogv" type="video/ogg">
</div>

###视频预设（Fallbacks）

就像`audio`元素一样，`video`元素的预设也是必要的，相同的格式，需要设置多个`source`元素。还有个可选的方案，使用[YouTube](http://www.youtube.com/)和[Vimeo](https://vimeo.com/)，来构建自己的播放器，将视频极其简单的上传到这些视频托管网站，然后再嵌入到自己网站。

```html
<video controls>
  <source src="earth.ogv" type="video/ogg">
  <source src="earth.mp4" type="video/mp4">
  <object type="application/x-shockwave-flash" data="player.swf?video=earth.mp4">
    <param name="movie" value="player.swf?video=earth.mp4">
    <p>This browser does not support the video format. Please <a href="earth.mp4" title="Earth video">download</a> the video.</p>
  </object>
</video>
```


<div class="code-box">
<h4>HTML5音频和视频文件格式</h4>
<p>浏览器是否支持<code>audio</code>和<code>video</code>元素是根据其内是否有该浏览器所支持的文件格式。每个浏览器对支持那种<code>audio</code>和<code>video</code>文件格式有着各自的<a href="https://developer.mozilla.org/En/Media_formats_supported_by_the_audio_and_video_elements">解释</a>。</p>
<p>将文件转换成不同的格式，在此有几个工具可以帮忙，线上的和桌面的都有。转换音频文件，web应用<a href="http://media.io/" title="media.io Audio Converter">media.io</a>可以胜任。转换视频文件桌面软件<a href="http://www.mirovideoconverter.com/" title="Miro Video Converter" rel="nofollow">Miro Video Converter</a>也可以满足需要。</p>
</div>

##图像和标题（Figure & Caption）

HTML5中新引入了`figure`和`figcaption`元素，用来语义化的标记有着同一主题的内容或者媒体，其内通常有一个标题。在HTML5之前使用无序列表来完成，无序列表虽然可以工作但是并不符合语义化的原则。

###图像（Figure）

块级`figure`元素用来包裹不同形式的媒体。它可以包裹图片、音频片段、视频、代码快、图表、插图，以及其他各种形式的媒体。`figure`元素中可能一次包含了多种形式的媒体。例如多个图片和视频。总得来说，`figure`元素不可以扰乱内容或者页面的可读性，可以将其移植页面的底部或者附录。

```html
<figure>
  <img src="images-audio-video/cows.jpg" alt="Brown and white cows in a field">
</figure>
```

<div class="code-box">
<h4>图像Demo</h4>
<figure style="width: 400px;">
    <img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field">
  </figure>
</div>

###图像标题（Figure Caption）

为了给`figure`元素标题或者说明，使用`figcaption`元素。`figcaption`元素可以出现在顶部、底部、或者在`figure`元素的任何地方，但是`figcaption`元素只容许出现一次。

```html
<figure>
  <img src="images-audio-video/cows.jpg" alt="Brown and white cows in a field">
  <figcaption>A couple of brown and white cows hanging out in a grass field.</figcaption>
</figure>
```

<div class="code-box">
<h4>图像和标题Demo</h4>
<figure style="width: 400px;">
    <img src="http://learn.hicc.me/images/2013/09/cows.jpg" alt="Brown and white cows in a field">
  </figure>
  <figcaption>A couple of brown and white cows hanging out in a grass field.</figcaption>
</div>


##资源
<ul class="col-2">
  <li><a href="http://dev.opera.com/articles/view/17-images-in-html/" title="Images in HTML" rel="nofollow">Images in HTML</a> via Dev.Opera</li>
  <li><a href="https://developer.mozilla.org/en/Using_HTML5_audio_and_video" title="Using HTML5 audio and video" rel="nofollow">HTML5 audio <abbr title="and">&amp;</abbr> video</a> via Mozilla Developer Network</li>
  <li><a href="https://developer.mozilla.org/En/HTML/Element/Audio" title="audio HTML5 Element" rel="nofollow">audio HTML5 Element</a> via Mozilla Developer Network</li>
  <li><a href="http://dev.opera.com/articles/view/introduction-html5-video/" title="Introduction to HTML5 video" rel="nofollow">Introduction to HTML5 Video</a> via Dev.Opera</li>
  <li><a href="http://html5doctor.com/the-figure-figcaption-elements/" title="The figure and figcaption elements" rel="nofollow">The figure <abbr title="and">&amp;</abbr> figcaption Elements</a> via HTML5 Doctor</li>
</ul>




