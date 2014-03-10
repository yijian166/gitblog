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

为了获取用户输入而了解[如何构建表单](http://htmldog.com/guides/htmlbeginner/forms/)是十分有必要的。在本文会讨论如何使用HTML元素来构建表单，哪些元素可以捕获不同类型的数据，以及如何使用CSS样式。在此不会深入信息如何在表单传递，以及如何在网站后台处理。表单处理是一个很深的主题，不在本文的讨论范围之内。

##初始化表单

在页面上开是一个表单必须使用`form`[元素](https://developer.mozilla.org/en/HTML/Element/form)。`form`元素表明了页面中那里将会出现控件元素。另外，`form`元素将表单内的元素都包裹其中，这点有点像`div`元素。

```html
<form action="#" method="foo">
···
</form>
```

在`form`元素上有几个属性可以使用，其中最常用的有两个，`action`和`methed`。表单中信息最终会被提交到到服务器处理，`action`属性中的值便是对应服务器的URI。而`methed`属性则是浏览器提交表单信息的HTTP方法。这两个`form`元素属性都是围绕数据提交和数据处理。

##文本输入和多段文本输入

谈到表单内的文本控件，只有几个元素可以用来获取数据。文本输入和多行文本输入专门用来手机文本或者基于字符串的数据。这样的数据包括段落文本内容、密码、手机号码等等。

###文本输入

获取用户输入文本最重要的元素之一便是`input`元素。`input`元素使用`type`属性决定了从特定控件中获取什么类型的数据信息。最常用的`type`属性值便是`text`，它的表现为一个单行的文本输入框。

在设置`type`属性时最好的做法是同时给`input`元素设置一个`name`属性。`name`属性为改控件命名，同时和input中的数据一并提交到服务器。

```html
<input type="text" name="sample_text_field">
```
<div class="code-box">
	<h4>文本输入Demo</h4>
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

####iOS中不同的input输入框(右侧为iOS7截图)

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

###多行文本输入

另一个获取文本数据的元素便是`textarea`元素。`textarea`元素与`input`元素不同的在于`textarea`元素是针对多行的大段文字的。并且`textarea`元素有这开始和结束标签可以包裹纯文本。因为`textarea`元素只接受一种类型的值因此`type`属性在此不必使用，但是同样可以使用`name`属性。

```html
<textarea name="sample_textarea">Sample textarea</textarea>
```

<div class="code-box">
<h4>多行输入Demo</h4>
<textarea name="sample_textarea">Sample textarea</textarea>
</div>

`textarea`元素有两个尺寸属性，`cols`设置宽度，`rows`设置高度。但是这两个属性都是相当老的属性了，现在可以使用CSS属性`width`和`height`达到同样的效果。

##多项选择输入和菜单

除了文本输入控件之外HTML还容许用户使用多项选择和下拉列表来选择数据。这些表单控件有不同的选项和元素，每种都有着不同的应用。

###单选按钮

单选按钮是一种快速而简单的方法来展示一个小的选项列表让用户快速做出决定。单选按钮只容许用户选择一个选项，而不是选择多个选项。

创建一个单选按钮，可以设置`input`元素的`type`属性为`radio`。单选按钮的每个选项的`name`属性值都应该相同，这样它们才能相互对应。对于文本输入框`input`的值取决于用户的输入，而对于单选按钮用户只是做一个简单的决定，因此是我们自己决定`input`的值。使用`value`属性我们可以为每一个`input`设置特定的值。

另外，为用户设置默认的选项，可以使用布尔属性`checked`。

```html
<input type="radio" name="day" value="Friday" checked> Friday
<input type="radio" name="day" value="Saturday"> Saturday
<input type="radio" name="day" value="Sunday"> Sunday
```
<div class="code-box">
<h4>单选按钮Demo</h4>
<input type="radio" name="day" value="Friday" checked> Friday
<input type="radio" name="day" value="Saturday"> Saturday
<input type="radio" name="day" value="Sunday"> Sunday
</div>

###复选框

复选框和单选按钮非常相似。复选框除了`type`属性为`checkbox`外其他属性和单选按钮一样。两者之间的区别是，复选框容许用户选择多个选项都对应一个控件的名称，而单选按钮则只容许选一个。

```html
<input type="checkbox" name="day" value="Friday" checked> Friday
<input type="checkbox" name="day" value="Saturday"> Saturday
<input type="checkbox" name="day" value="Sunday"> Sunday
```

<div class="code-box">
<h4>复选框Demo</h4>
<input type="checkbox" name="day" value="Friday" checked> Friday
<input type="checkbox" name="day" value="Saturday"> Saturday
<input type="checkbox" name="day" value="Sunday"> Sunday
</div>

###下拉列表

在可用的方法中下拉列表是提供用户长串选项的最好方式。如果使用单选按钮将国家每个州都输出在一个页面中将会是一个凌乱而让人气馁的列表。下拉列表为长串列选择提供了一个绝佳的显示方式。

使用`select`和`option`元素便可以创建出一个下拉列表。每个选项用`option`元素构成，在用`select`元素包裹所有的`option`元素，然后你可以为`select`元素设置`name`属性。

菜单中每个独立的选项都用`option`元素编码。`option`元素将会包裹菜单中的选项文本。另外，每个独立的选项的`option`元素都需要设置`value`属性。

就像单项按钮和复选框的布尔睡下`checked`。下拉列表可以使用布尔属性`selected`来为用户设置默认值。

```html
<select name="day">
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>
```

<div class="code-box">
<h4>下拉列表Demo</h4>
<select name="day">
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select></div>

###多重选择

在标准的下拉列表中在`select`元素增加布尔属性`multiple`即可容许用户多选菜单中选项。另外，可以设置一个或者多个布尔属性`selected`来为用户设置默认的选中项。

`select`元素的高度和宽度可以使用CSS属性控制，最好方便用户多选选项。还值得提的是用户想要多选选项，在点击的同时需要同时按着<i>Ctrl/command<i>或者<i>shift<i>键。

```html
<select name="day" multiple>
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>
```
<div class="code-box">
<h4>多重选择Demo</h4>
<select name="day" multiple>
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>
</div>

##表单按钮


使用`value`属性来设置选项的文本。使用CSS属性例如`background`、`border-radius`、`box-shadow`等可以将单选按钮设置成你想要的效果。

```html
<input type="submit" name="submit" value="Submit Form">
```
