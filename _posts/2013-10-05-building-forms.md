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
</select>
</div>


###多重选择

在标准的下拉列表中在`select`元素增加布尔属性`multiple`即可容许用户多选菜单中选项。另外，可以设置一个或者多个布尔属性`selected`来为用户设置默认的选中项。

`select`元素的高度和宽度可以使用CSS属性控制，最好方便用户多选选项。还值得提的是用户想要多选选项，在点击的同时需要同时按着<i>Ctrl/command</i>或者<i>shift</i>键。


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

当用户输入了所需的信息之后，按钮就可以让他们采取行动。最常见的便是一个提交按钮用来处理数据。一个重置按钮用来清楚数据。

###提交按钮

当用户填完表单之后点击提交按钮来处理数据。提交按钮使用`type`属性为`submit`或者`image`的`input`元素。`submit`是最常用的因为它使用简单并且提供了大部分的功能。
`image`值用来指定一个图片为一个提交按钮，然而随着CSS的使用，该值的使用逐渐减少。

使用`value`属性来设置选项的文本。使用CSS属性例如`background`、`border-radius`、`box-shadow`等可以将单选按钮设置成你想要的效果。

```html
<input type="submit" name="submit" value="Submit Form">
```
<div class="code-box post-8-input-btn">
<h4>提交按钮Demo</h4>
<input type="submit" name="submit" value="Submit Form">
</div>

###重置按钮

与提交订单相反的是，用户可能使用重置按钮来重置表单。重置按钮和提交按钮的代码类似，只是其`type`值为`reset`。

重置按钮有着非常强烈的动作，无论是网站主还是用户都不想用，因此重置按钮越来越不受欢迎。用户在花了很长时间填写表单之后在提交的时候误点成重置按钮，而用户重新填写一次表单的机率会非常少。在使用重置表单的时候要考虑好这些后果。

```html
<input type="reset" name="reset" value="Reset Form">
```

<div class="code-box post-8-input-btn">
<h4>重置按钮Demo</h4>
<input type="reset" name="reset" value="Reset Form">
</div>

###其他类型的input

除去上文所说的，`input`元素还有些其他的用例。其中的两个有传递隐藏数据和附加文件。

####Hide Input

隐藏的`input`可以在不显示给用户的情况下传递数据给服务器。隐藏的`input`经典的用法有跟踪代码(tracking codes)，密钥(keys)以及其他对用户不可见但是有利于整个网站的信息。这些信息不会在页面中显示，但是它可以通过查看网页源代码来看到。也就是说，在此不应该带有敏感的或者安全性质的信息。

设置`type`属性为`hidden`即可创建一个隐藏的`input`元素，另外，你还应该给他们设置合适的`name`和`value`属性。

```html
<input type="hidden" name="tracking_code" value="abc_123">
```

####File Input(文件上传)

允许用户附加文件到表单，就像给邮件添加邮件一样，可以设置`type`属性为`file`。上传文件常见在社交网络或者应用中上传图片或者文件。

然而，通过CSS来设置文件上传控件的样式是个艰巨的任务。每个浏览器都有自己默认的样式，而且几乎不能更改这些样式。JavaScript以及其他的方案也可以实现文件上传，但是这些都有点难以创建。

```html
<input type="file" name="file">
```

<div class="code-box">
<h4>文件上传Demo</h4>
<input type="file" name="file">
</div>

###组织表单元素

知道了如何通过input获取数据仅仅完成了一半，以一种可用的方式将这些表单元素和控件组织起来就是另外一半。用户理解了表单想要问什么，并且知道怎么回答，表单才有意义。我们可以使用`label`，`fieldset`，`legend`来构建一个更好的表单以此来引导用户完成任务。

####标签(Label)

标签为表单元素提供了说明，或者标题。使用`label`元素开创建标签，标签应该包含所遇表单元素或者控件的描述文本。也应该设置`for`属性。`label`元素`for`属性的值应该和所属表单元素的`id`属性的值相同，以此来将标签元素和表单元素绑在一块，容许用户点击`label`元素，所对应的表单元素即可获得焦点。

```html
<label for="username">Username</label>
<input type="text" name="username" id="username">
```
<div class="code-box">
<h5>标签Demo</h5>
<label for="username">Username</label>
<input type="text" name="username" id="username">
</div>

当单选按钮或者复选框使用标签的时候，可以将`input`元素包裹在`label`元素之内。这样就可以免去设置`for`属性和`id`属性。


```html
<label><input type="radio" name="day" value="Friday" checked> Friday</label>
<label><input type="radio" name="day" value="Saturday"> Saturday</label>
<label><input type="radio" name="day" value="Sunday"> Sunday</label>

```
<div class="code-box">
<h4>标签单选按钮Demo</h4>
<label><input type="radio" name="day" value="Friday" checked> Friday</label>
<label><input type="radio" name="day" value="Saturday"> Saturday</label>
<label><input type="radio" name="day" value="Sunday"> Sunday</label>
</div>

####控件组(Fieldset)

控件组(Fieldset)将表单标签和元素组合成一个块。就像`div`元素或者其他结构性的元素，`fieldset`元素是块级元素，包裹相关联的元素，只是`fieldset`特别针对`form`元素内的元素。`fieldset`元素默认有个边框，可以通过CSS更改。

```html
<fieldset>
  <label for="username">Username</label>
  <input type="text" name="username" id="username">
  <label for="password">Password</label>
  <input type="text" name="password" id="password">
</fieldset>
```
<div class="code-box post8-input-border">
<h5>控件组Demo</h5>
<fieldset>
  <label for="username">Username</label>
  <input type="text" name="username" id="username">
  <label for="password">Password</label>
  <input type="text" name="password" id="password">
</fieldset>
</div>


####Legend

Legend是对`fieldset`元素的说明或者标题。`legend`元素包裹了`fieldset`元素之内控件的说明描述。在HTML代码中`legend`元素应当紧跟`fieldset`元素的起始标签。`legend`元素默认作为`fieldset`元素边框的一部分显示在左上角。`legend`元素的样式也可以通过CSS来更改。

```html
<fieldset>
  <legend>Login</legend>
  <label for="username">Username</label>
  <input type="text" name="username" id="username">
  <label for="password">Password</label>
  <input type="text" name="password" id="password">
</fieldset>
```

<div class="code-box post8-input-border">
<h5>Legend Demo</h5>
<fieldset>
  <legend>Login</legend>
  <label for="username">Username</label>
  <input type="text" name="username" id="username">
  <label for="password">Password</label>
  <input type="text" name="password" id="password">
</fieldset>
</div>

###Form和input的属性

为了适配所有不同的表单，input，和控件，在此又许多的属性和对应的值。这些属性和值有着很多不同的功能，其中又禁止控件，增加表单验证，等等，下面是较为常用也较为有用的属性。

####Disable

设置布尔属性`disabled`可以关闭元素和控件的交互或者输入。在表单提交的时候被禁元素不发送任何数据。

设置`disabled`属性到`fieldset`元素，将会禁用`fieldset`元素所有的控件。如果控件的`type`属性的值为`hidden`，将不会理会`disabled`属性。

```html
<label for="username">Username</label>
<input type="text" name="username" id="username" disabled>
```
<div class="code-box">
<h5><code>disabled</code>属性Demo</h5>
<label for="username">Username</label>
<input type="text" name="username" id="username" disabled class="post8-input-disabled">
</div>

####Placeholder

`input`元素内的HTML5属性`placeholder`为控件提供了提示，提示会在控件<del>被点击或者获得焦点</del>有文字输入的时候消失，`placeholder`属性只能在`type`属性为`text`，`email`，`search`，`tel`和`url`的`input`元素内使用。

`placeholder`属性和`value`属性的区别在于，`value`属性值会一直存在除非用户主动删除。`value`属性值很适合预填充(pre-poplating)的值，譬如用户的个人信息，而不是建议的值。两者之间的额区别可以看下面。

```html
<label for="username">Username placeholder</label>
<input type="text" name="username" id="username" placeholder="Holder">
```
<div class="code-box">
<h5><code>placeholder</code>属性Demo</h5>
<label for="username-4">Username placeholder</label>
  <input type="text" name="username" id="username-4" placeholder="Holder">
  <label for="username-5">Username value</label>
  <input type="text" name="username" id="username-5" value="Value">
</div>

####Required

HTML5属性`required`强制元素在提交的时候必须有值。当一个元素或者控件内没值的时候会出现错误信息提示用户，要求他们填写所需的值。目前浏览器所显示的错误信息的样式还不可使用CSS更改。而对于元素，可以使用`:optional``:required`的CSS伪类来选择。

当控件需要特定类型的值的时候验证也会发生。例如，`type`属性为`email`将的`input`元素将不仅需要有值而且改值需要符合邮箱的格式。

```html
<label for="name">Name</label>
<input type="text" name="name" id="name" required>
```
<div class="code-box">
<h5><code>required</code>属性Demo</h5>
<form>
    <label for="name">Name</label>
    <input type="text" name="name" id="name" required="">
    <label for="email">Email</label>
    <input type="email" name="email" id="email" required="">
    <input type="submit" name="submit" value="Send">
</form>
</div>

####其他属性

下面列举了一些其他的表单，input属性，可以在必要时深入研究。

-	`accept`
-	`formaction`
-	`formnovalidate`
-	`maxlength`
-	`readonly`
-	`autocomplete`
-	`formenctype`
-	`formtarget`
-	`min`
-	`selectionDirection`
-	`autofoucus`
-	`formmethod`
-	`max`
-	`pattern`
-	`step`


<div class="code-box post8-demo">
<h3>登录表单Demo<h3>
<h4>html</h4>
<div class="highlight"><pre><code class="html language-html" data-lang="html"><span class="nt">&lt;form&gt;</span>
  <span class="nt">&lt;label</span> <span class="na">for=</span><span class="s">"login_username"</span><span class="nt">&gt;</span>Username<span class="nt">&lt;/label&gt;</span>
  <span class="nt">&lt;input</span> <span class="na">type=</span><span class="s">"text"</span> <span class="na">name=</span><span class="s">"login_username"</span> <span class="na">id=</span><span class="s">"login_username"</span><span class="nt">&gt;</span>
  <span class="nt">&lt;label</span> <span class="na">for=</span><span class="s">"login_password"</span><span class="nt">&gt;</span>Password<span class="nt">&lt;/label&gt;</span>
  <span class="nt">&lt;input</span> <span class="na">type=</span><span class="s">"password"</span> <span class="na">name=</span><span class="s">"login_password"</span> <span class="na">id=</span><span class="s">"login_password"</span><span class="nt">&gt;</span>
  <span class="nt">&lt;fieldset&gt;</span>
    <span class="nt">&lt;input</span> <span class="na">type=</span><span class="s">"submit"</span> <span class="na">name=</span><span class="s">"login_submit"</span> <span class="na">id=</span><span class="s">"login_submit"</span> <span class="na">value=</span><span class="s">"Login"</span><span class="nt">&gt;</span>
    <span class="nt">&lt;label&gt;&lt;input</span> <span class="na">type=</span><span class="s">"checkbox"</span> <span class="na">name=</span><span class="s">"login_remember"</span> <span class="na">id=</span><span class="s">"login_remember"</span><span class="nt">&gt;</span> Stay signed in<span class="nt">&lt;/label&gt;</span>
  <span class="nt">&lt;/fieldset&gt;</span>
<span class="nt">&lt;/form&gt;</span>
</code></pre></div>
<h4>css</h4>
<div class="highlight"><pre><code class="css language-css" data-lang="css"><span class="nt">form</span> <span class="p">{</span>
  <span class="k">background</span><span class="o">:</span> <span class="n">linear</span><span class="o">-</span><span class="n">gradient</span><span class="p">(</span><span class="k">top</span><span class="o">,</span> <span class="m">#fff</span><span class="o">,</span> <span class="m">#f8f8f8</span><span class="p">);</span>
  <span class="k">border</span><span class="o">:</span> <span class="m">1px</span> <span class="k">solid</span> <span class="m">#d0d2d5</span><span class="p">;</span>
  <span class="k">border-bottom</span><span class="o">:</span> <span class="m">1px</span> <span class="k">solid</span> <span class="m">#bebfc2</span><span class="p">;</span>
  <span class="k">border</span><span class="o">-</span><span class="n">radius</span><span class="o">:</span> <span class="m">4px</span><span class="p">;</span>
  <span class="k">margin</span><span class="o">:</span> <span class="m">0</span> <span class="m">0</span> <span class="m">20px</span> <span class="m">0</span><span class="p">;</span>
  <span class="k">padding</span><span class="o">:</span> <span class="m">20px</span><span class="p">;</span>
  <span class="k">width</span><span class="o">:</span> <span class="m">212px</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">label</span> <span class="p">{</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#404853</span><span class="p">;</span>
  <span class="k">display</span><span class="o">:</span> <span class="k">block</span><span class="p">;</span>
  <span class="k">font-weight</span><span class="o">:</span> <span class="k">bold</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">input</span> <span class="p">{</span>
  <span class="k">background</span><span class="o">:</span> <span class="m">#fff</span><span class="p">;</span>
  <span class="k">border</span><span class="o">:</span> <span class="m">1px</span> <span class="k">solid</span> <span class="m">#c6c9cc</span><span class="p">;</span>
  <span class="k">border</span><span class="o">-</span><span class="n">radius</span><span class="o">:</span> <span class="m">4px</span><span class="p">;</span>
  <span class="n">box</span><span class="o">-</span><span class="n">shadow</span><span class="o">:</span> <span class="k">inset</span> <span class="m">0</span> <span class="m">1px</span> <span class="m">1px</span> <span class="n">rgba</span><span class="p">(</span><span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">.</span><span class="m">1</span><span class="p">)</span><span class="o">,</span> <span class="m">0</span> <span class="m">1px</span> <span class="m">0</span> <span class="m">#fff</span><span class="p">;</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#555</span><span class="p">;</span>
  <span class="k">font</span><span class="o">:</span> <span class="m">13px</span><span class="o">/</span><span class="m">20px</span> <span class="s1">'Droid Sans'</span><span class="o">,</span> <span class="n">Arial</span><span class="o">,</span> <span class="s1">'Helvetica Neue'</span><span class="o">,</span> <span class="s1">'Lucida Grande'</span><span class="o">,</span> <span class="k">sans-serif</span><span class="p">;</span>
  <span class="k">margin</span><span class="o">:</span> <span class="m">0</span> <span class="m">0</span> <span class="m">20px</span> <span class="m">0</span><span class="p">;</span>
  <span class="k">padding</span><span class="o">:</span> <span class="m">5px</span><span class="p">;</span>
  <span class="k">width</span><span class="o">:</span> <span class="m">200px</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">fieldset</span> <span class="p">{</span>
  <span class="k">background</span><span class="o">:</span> <span class="n">linear</span><span class="o">-</span><span class="n">gradient</span><span class="p">(</span><span class="k">top</span><span class="o">,</span> <span class="m">#ebeced</span><span class="o">,</span> <span class="m">#dedfe0</span><span class="p">);</span>
  <span class="k">border</span><span class="o">:</span> <span class="k">none</span><span class="p">;</span>
  <span class="k">border-top</span><span class="o">:</span> <span class="m">1px</span> <span class="k">solid</span> <span class="m">#d0d2d5</span><span class="p">;</span>
  <span class="k">border</span><span class="o">-</span><span class="n">radius</span><span class="o">:</span> <span class="m">0</span> <span class="m">0</span> <span class="m">4px</span> <span class="m">4px</span><span class="p">;</span>
  <span class="n">box</span><span class="o">-</span><span class="n">shadow</span><span class="o">:</span> <span class="k">inset</span> <span class="m">0</span> <span class="m">1px</span> <span class="m">0</span> <span class="n">rgba</span><span class="p">(</span><span class="m">255</span><span class="o">,</span> <span class="m">255</span><span class="o">,</span> <span class="m">255</span><span class="o">,</span> <span class="m">0</span><span class="o">.</span><span class="m">75</span><span class="p">);</span>
  <span class="k">margin</span><span class="o">:</span> <span class="m">5px</span> <span class="m">0</span> <span class="m">-20px</span> <span class="m">-20px</span><span class="p">;</span>
  <span class="k">padding</span><span class="o">:</span> <span class="m">18px</span> <span class="m">20px</span><span class="p">;</span>
  <span class="k">width</span><span class="o">:</span> <span class="m">212px</span>
<span class="p">}</span>
<span class="nt">fieldset</span> <span class="nt">input</span> <span class="p">{</span>
  <span class="k">margin</span><span class="o">:</span> <span class="m">0</span><span class="p">;</span>
  <span class="k">width</span><span class="o">:</span> <span class="k">auto</span><span class="p">;</span>
<span class="p">}</span>
<span class="nf">#login_submit</span> <span class="p">{</span>
  <span class="k">background</span><span class="o">:</span> <span class="n">linear</span><span class="o">-</span><span class="n">gradient</span><span class="p">(</span><span class="k">top</span><span class="o">,</span> <span class="m">#687587</span><span class="o">,</span> <span class="m">#404853</span><span class="p">);</span>
  <span class="k">border</span><span class="o">:</span> <span class="k">none</span><span class="p">;</span>
  <span class="n">box</span><span class="o">-</span><span class="n">shadow</span><span class="o">:</span> <span class="k">inset</span> <span class="m">0</span> <span class="m">1px</span> <span class="m">2px</span> <span class="n">rgba</span><span class="p">(</span><span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">.</span><span class="m">3</span><span class="p">)</span><span class="o">,</span> <span class="m">0</span> <span class="m">1px</span> <span class="m">0</span> <span class="n">rgba</span><span class="p">(</span><span class="m">255</span><span class="o">,</span> <span class="m">255</span><span class="o">,</span> <span class="m">255</span><span class="o">,</span> <span class="m">0</span><span class="o">.</span><span class="m">75</span><span class="p">);</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#fff</span><span class="p">;</span>
  <span class="k">font-weight</span><span class="o">:</span> <span class="k">bold</span><span class="p">;</span>
  <span class="k">float</span><span class="o">:</span> <span class="k">left</span><span class="p">;</span>
  <span class="k">padding</span><span class="o">:</span> <span class="m">5px</span> <span class="m">10px</span><span class="p">;</span>
  <span class="k">text-shadow</span><span class="o">:</span> <span class="m">0</span> <span class="m">-1px</span> <span class="m">0</span> <span class="n">rgba</span><span class="p">(</span><span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">.</span><span class="m">6</span><span class="p">);</span>
<span class="p">}</span>
<span class="nf">#login_submit</span><span class="nd">:hover</span> <span class="p">{</span>
  <span class="k">background</span><span class="o">:</span> <span class="n">linear</span><span class="o">-</span><span class="n">gradient</span><span class="p">(</span><span class="k">top</span><span class="o">,</span> <span class="m">#5a6675</span><span class="o">,</span> <span class="m">#333942</span><span class="p">);</span>
<span class="p">}</span>
<span class="nf">#login_submit</span><span class="nd">:active</span> <span class="p">{</span>
  <span class="k">background</span><span class="o">:</span> <span class="m">#333942</span><span class="p">;</span>
  <span class="n">box</span><span class="o">-</span><span class="n">shadow</span><span class="o">:</span> <span class="k">inset</span> <span class="m">0</span> <span class="m">1px</span> <span class="m">2px</span> <span class="n">rgba</span><span class="p">(</span><span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">,</span> <span class="m">0</span><span class="o">.</span><span class="m">75</span><span class="p">)</span><span class="o">,</span> <span class="m">0</span> <span class="m">1px</span> <span class="m">0</span> <span class="n">rgba</span><span class="p">(</span><span class="m">255</span><span class="o">,</span> <span class="m">255</span><span class="o">,</span> <span class="m">255</span><span class="o">,</span> <span class="m">0</span><span class="o">.</span><span class="m">75</span><span class="p">);</span>
<span class="p">}</span>
<span class="nt">fieldset</span> <span class="nt">label</span> <span class="p">{</span>
  <span class="k">color</span><span class="o">:</span> <span class="m">#888</span><span class="p">;</span>
  <span class="k">cursor</span><span class="o">:</span> <span class="k">pointer</span><span class="p">;</span>
  <span class="k">float</span><span class="o">:</span> <span class="k">left</span><span class="p">;</span>
  <span class="k">font-size</span><span class="o">:</span> <span class="m">12px</span><span class="p">;</span>
  <span class="k">font-weight</span><span class="o">:</span> <span class="k">normal</span><span class="p">;</span>
  <span class="k">margin</span><span class="o">:</span> <span class="m">5px</span> <span class="m">0</span> <span class="m">0</span> <span class="m">20px</span><span class="p">;</span>
<span class="p">}</span>
<span class="nt">fieldset</span> <span class="nt">label</span> <span class="nt">input</span> <span class="p">{</span>
  <span class="k">margin</span><span class="o">:</span> <span class="m">-2px</span> <span class="m">2px</span> <span class="m">0</span> <span class="m">0</span><span class="p">;</span>
  <span class="k">padding</span><span class="o">:</span> <span class="m">0</span><span class="p">;</span>
<span class="p">}</span>
</code></pre></div>
<h4>Demo</h4>
<form>
    <label for="login_username">Username</label>
    <input type="text" name="login_username" id="login_username" required>
    <label for="login_password">Password</label>
    <input type="password" name="login_password" id="login_password" required>
    <fieldset>
      <input type="submit" name="login_submit" id="login_submit" value="Login">
      <label><input type="checkbox" name="login_remember" id="login_remember"> Stay signed in</label>
    </fieldset>
  </form>
</div>


##资源

<ul class="col-2">
  <li><a href="http://htmldog.com/guides/htmlbeginner/forms/" title="Forms" rel="nofollow">Forms</a> via HTML Dog</li>
  <li><a href="https://developer.mozilla.org/en/HTML/Element/form" title="Form" rel="nofollow">Form Element</a> via Mozilla Developer Network</li>
  <li><a href="https://developer.mozilla.org/en/HTML/Element/input" title="Input" rel="nofollow">Input Element</a> via Mozilla Developer Network</li>
  <li><a href="http://diveinto.html5doctor.com/forms.html" title="A Form of Madness" rel="nofollow">A Form of Madness</a> via Dive Into HTML5</li>
  <li><a href="http://twitter.github.com/bootstrap/base-css.html#forms">Form Examples</a> via Twitter Bootstrap</li>
</ul>




