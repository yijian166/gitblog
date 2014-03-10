---
layout: post
title: 创建表单
categories: [html-css]
---

{{ page.title }}
================

<p class="meta">LESSON 8 · 2013/10/5</p>

英文原文：[Building Forms](http://learn.shayhowe.com/html-css/building-forms)

表单是互联网很重要的一部分，它可以用来为网站获取用户信息，处理请求。通过使用控件和字段，表单可以请求少量的信息，像搜索检索，也可以请求大量信息，先航班查询，或者订单信息。

为了获取用户输入而了解[如何构建表单]()是十分有必要的。在本文会讨论如何使用HTML元素来构建表单，哪些元素可以捕获不同类型的数据，以及如何使用CSS样式。在此不会深入信息如何在表单传递，以及如何在网站后台处理。表单处理是一个很深的主题，不在本文的讨论范围之内。

##初始化表单

在页面上开是一个表单必须使用`form`[元素](https://developer.mozilla.org/en/HTML/Element/form)。`form`元素表明了页面中那里将会出现控件元素。另外，`form`元素将表单内的元素都包裹其中，这点有点像`div`元素。

```div
<form action=“#” method="foo">
···
</form>
```

在`form`元素上有几个属性可以使用，其中最常用的有两个，`action`和`methed`。表单中信息最终会被提交到到服务器处理，`action`属性中的值便是对应服务器的URI。而`methed`属性则是浏览器提交表单信息的HTTP方法。这两个`form`元素属性都是围绕数据提交和数据处理。

###文本输入和多段文本输入

谈到表单内的文本控件，只有几个元素可以用来获取数据。文本输入和多行文本输入专门用来手机文本或者基于字符串的数据。这样的数据包括段落文本内容、密码、手机号码等等。

####文本输入

获取用户输入文本最重要的元素之一便是`input`元素。`input`元素使用`type`属性决定了从特定控件中获取什么类型的数据信息。最常用的`type`属性值便是`text`，它的表现为一个单行的文本输入框。

在设置`type`属性时最好的做法是同时给`input`元素设置一个`name`属性。`name`属性为改控件命名，同时和input中的数据一并提交到服务器。

```html
<input type="text" name="sample_text_field">
```
<div class="code-box">
	<h5>文本输入Demo</h5>
	<input type="text" name="sample_text_field">
</div>

需要注意的是`input`元素是自闭的，也就是它只有一个标签而且不会包裹任何内容。

最初`input`元素之后两个基于文本的`type`属性，`text`和`password`，`password`属性针对密码输入。最新在HTML5中则带来了一些新的`type`属性值以及[表单更新](http://diveinto.html5doctor.com/forms.html)。这些新增的值为输入提供了一个更好的语义化上下文也就为用户提供了一个更好的输入体验。当浏览器不理解新的`type`属性值的时候，它会自动降级到`text`属性值。下面便是新的HTML5输入类型：

- color
- date
- datetime
- datetime-local
- email
- month
- number
- range
- search
- tel
- time
- url
- week

#####iOS中不同的input输入框(右侧为iOS7截图)

![ios date输入框](http://learn.hicc.me/images/2014/03/date.jpg)

ios date输入框

![ios time输入框](http://learn.hicc.me/images/2014/03/time.jpg)

ios time输入框

![ios email输入框](http://learn.hicc.me/images/2014/03/email.jpg)

ios url输入框

![ios date输入框](http://learn.hicc.me/images/2014/03/url.jpg)

ios url输入框

![ios number输入框](http://learn.hicc.me/images/2014/03/number.jpg)

ios number输入框

![ios date输入框](http://learn.hicc.me/images/2014/03/tel.jpg)

ios tel输入框

####多行文本输入

