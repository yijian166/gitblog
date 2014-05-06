---
layout: post
title: 使用表格来组织数据
categories: [html-css]
---

{{ page.title }}
================

<p class="meta">LESSON 9 · 2014/03/19</p>

英文原文：[organizing-data-tables](http://learn.shayhowe.com/html-css/organizing-data-tables)

最初HTML问世的时候表格无处不在，是网站建设的主要方式。它们被用来定位内容以及构建一个页面的整体布局。幸亏我们已经走过了这段蛮长的道路，现在表格是、应该、只用于[组织数据](http://dev.opera.com/articles/view/19-html-tables/)。

当处理大量的表格式数据的时候，表格是其显示的基础。使用表格可以让数据更加的容易阅读和消化，让用户对数据能有个全局的理解。

表格用于数据展示而不是页面设计的转变仍然有些挑战。在HTML中表格如何被构建这在很大程度上取决于数据以及这些数据如何展示。除了在HTML中的标记之外，表格还需要使用CSS来对其施加样式，以此来让样式变得更加直观易懂。

##创建表格

一般来说表格是由行和列构成的，这些行和列相互交叉。在HTML中，需要几个元素来创建一个表格，至少需要`table`，`tr`，`td`元素，更进一步的话，还需要`th`元素，将这些元素组合则可创建一个完整的表格。

###表格

在页面中初始化一个表格需要使用`table`元素，使用`table`元素表示其内的数据将会显示在两个或者更多的维度。`table`元素只是用来初始化，还需要在内随着内容包裹表格行。

```html
<table>
  ...
</table>
```

###表格行

在HTML中定义了表格之后，使用`tr`元素增加表格的行。一个表格可以包含很多个表格行(`tr`元素)，根据数据的数量，表格行可以变得很高。表格行内的数据则使用`td`元素添加，使用`th`元素添加表头。

```html
<table>
  <tr>
    ...
  </tr>
  <tr>
    ...
  </tr>
</table>
```

###表格数据

在表格中添加数据的最好方法便是使用`td`元素。`td`元素创建了个一个单元格。表格行内`td`元素的数量也就是表格列的数量。当然如果单元格内内容是表头内容则应该使用`th`元素而不是`td`元素。

```html
<table>
  <tr>
    <td>Date</td>
    <td>Opponent</td>
    <td>Location</td>
    <td>Time</td>
  </tr>
  <tr>
    <td>Monday, March 5th</td>
    <td>Indiana Pacers</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Wednesday, March 7th</td>
    <td>Milwaukee Bucks</td>
    <td>Bradley Center, Milwaukee, WI</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Thursday, March 8th</td>
    <td>Orlando Magic</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Saturday, March 10th</td>
    <td>Utah Jazz</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
</table>
```

<div class="code-box post9-table">
<h3>表格数据</h3>
<table>
  <tr>
    <td>Date</td>
    <td>Opponent</td>
    <td>Location</td>
    <td>Time</td>
  </tr>
  <tr>
    <td>Monday, March 5th</td>
    <td>Indiana Pacers</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Wednesday, March 7th</td>
    <td>Milwaukee Bucks</td>
    <td>Bradley Center, Milwaukee, WI</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Thursday, March 8th</td>
    <td>Orlando Magic</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Saturday, March 10th</td>
    <td>Utah Jazz</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
</table>
</div>

###表头

`th`元素用于指定表格的表头。表头元素的工作方式很像是单元格，而使用表头的意义在于表头为表格提供了语义化的意义，表明了其内的数据是标题。这样就和标题元素`h1`之与段落元素`p`一样，只是标题元素可以置于段落标签之内，而表头不能这样做。使用标题标签还可以提供更简单的办法来对标题施加样式，对于表头也是如此。

表格的行和列都可以有表头，`scope`属性专门用来指定该表头是属于行还是列的，`scope`属性的值`row`，`col`，`rowgroup`，`colgroup`中最常用的`row`和`col`分别表示了属于行和列的表头。

<div class="code-box">
<h4><code>headers</code>属性</h4>
<p><code>headers</code>属性和<code>scope</code>属性非常相似。默认情况下<code>scope</code>属性只用于<code>th</code>元素之上。而如过一个单元格，无论是<code>th</code>还是<code>td</code>需要和另外一个表头关联就需要使用<code>headers</code>属性。<code>th</code>或者<code>td</code>元素中<code>headers</code>属性的值需要和所关联单元格的<code>id</code>相匹配。</p>
</div>

另外，默认情况下表头回事粗体和居中。如果需要可以使用CSS样式覆盖。

```html
<table>
  <tr>
    <th scope="col">Date</th>
    <th scope="col">Opponent</th>
    <th scope="col">Location</th>
    <th scope="col">Time</th>
  </tr>
  <tr>
    <td>Monday, March 5th</td>
    <td>Indiana Pacers</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Wednesday, March 7th</td>
    <td>Milwaukee Bucks</td>
    <td>Bradley Center, Milwaukee, WI</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Thursday, March 8th</td>
    <td>Orlando Magic</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Saturday, March 10th</td>
    <td>Utah Jazz</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
</table>
```

<div class="code-box post9-table">
<h4>表头Demo</h4>
<table>
  <tr>
    <th scope="col">Date</th>
    <th scope="col">Opponent</th>
    <th scope="col">Location</th>
    <th scope="col">Time</th>
  </tr>
  <tr>
    <td>Monday, March 5th</td>
    <td>Indiana Pacers</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Wednesday, March 7th</td>
    <td>Milwaukee Bucks</td>
    <td>Bradley Center, Milwaukee, WI</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Thursday, March 8th</td>
    <td>Orlando Magic</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
  <tr>
    <td>Saturday, March 10th</td>
    <td>Utah Jazz</td>
    <td>United Center, Chicago, IL</td>
    <td>7:00 PM</td>
  </tr>
</table>
</div>

###合并单元格

有时候两个或者多个单元格需要合并成一个单元格，或许是因为相邻的单元格内容一样，也或许是处于样式的考虑。在此我们可以使用`colspan`和`rowspan`属性，这两个熟悉可以用到表格数据或者表头上。

`colspan`属性用于需要跨列合并的单元格，`rowspan`则用于需要跨行合并的单元格。两者都只接受整数的值，表示跨的单元格格数，`1`是默认的值。

```html
<table>
  <tr>
    <th scope="col">Date</th>
    <th scope="col">Opponent</th>
    <th scope="col">Location</th>
    <th scope="col">Time</th>
  </tr>
  <tr>
    <td>Monday, March 5th</td>
    <td>Indiana Pacers</td>
    <td>United Center, Chicago, IL</td>
    <td rowspan="4">7:00 PM</td>
  </tr>
  <tr>
    <td>Wednesday, March 7th</td>
    <td colspan="2">Milwaukee Bucks, Bradley Center, Milwaukee, WI</td>
  </tr>
  <tr>
    <td>Thursday, March 8th</td>
    <td>Orlando Magic</td>
    <td rowspan="2">United Center, Chicago, IL</td>
  </tr>
  <tr>
    <td>Saturday, March 10th</td>
    <td>Utah Jazz</td>
  </tr>
</table>
```

<div class="code-box post9-table">
<h4>合并单元格Demo</h4>
<table>
  <tr>
    <th scope="col">Date</th>
    <th scope="col">Opponent</th>
    <th scope="col">Location</th>
    <th scope="col">Time</th>
  </tr>
  <tr>
    <td>Monday, March 5th</td>
    <td>Indiana Pacers</td>
    <td>United Center, Chicago, IL</td>
    <td rowspan="4">7:00 PM</td>
  </tr>
  <tr>
    <td>Wednesday, March 7th</td>
    <td colspan="2">Milwaukee Bucks, Bradley Center, Milwaukee, WI</td>
  </tr>
  <tr>
    <td>Thursday, March 8th</td>
    <td>Orlando Magic</td>
    <td rowspan="2">United Center, Chicago, IL</td>
  </tr>
  <tr>
    <td>Saturday, March 10th</td>
    <td>Utah Jazz</td>
  </tr>
</table>
</div>

##表格结构

知道如何创建一个表格以及安排数据是一个非常强大的，也是每个前端工程师都需要掌握的技能。除了上述的表格构建要点之外，还有其他的元素来帮助在表格中[组织数据](http://www.456bereastreet.com/archive/200410/bring_on_the_tables/)，这些元素包括`caption`，`thead`，`tfoot`以及`tbody`。

###表格标题

使用`caption`元素来为表格提供说明或者标题。表格标题让用户明白表格所包含的东西。`caption`需要紧跟在`table`标签之后。它的位置默认在表格的顶部，当然也可以使用CSS来改变。如果表格在`figure`元素之内，那么就需要用`figcaption`元素替换`caption`元素。

```html
<table>
  <caption>Chicago Bulls Schedule - Week of March 5th</caption>
  ...
</table>
```
<div class="code-box post9-table post9-table-caption">
<h4>表格标题Demo</h4>
<table>
    <caption>Chicago Bulls Schedule - Week of March 5th</caption>
    <tbody><tr>
      <th scope="col">Date</th>
      <th scope="col">Opponent</th>
      <th scope="col">Location</th>
      <th scope="col">Time</th>
    </tr>
    <tr>
      <td>Monday, March 5th</td>
      <td>Indiana Pacers</td>
      <td>United Center, Chicago, IL</td>
      <td>7:00 PM</td>
    </tr>
    <tr>
      <td>Wednesday, March 7th</td>
      <td>Milwaukee Bucks</td>
      <td>Bradley Center, Milwaukee, WI</td>
      <td>7:00 PM</td>
    </tr>
    <tr>
      <td>Thursday, March 8th</td>
      <td>Orlando Magic</td>
      <td>United Center, Chicago, IL</td>
      <td>7:00 PM</td>
    </tr>
    <tr>
      <td>Saturday, March 10th</td>
      <td>Utah Jazz</td>
      <td>United Center, Chicago, IL</td>
      <td>7:00 PM</td>
    </tr>
  </tbody></table>
</div>

###表格`thead`，`tbody`，`tfoot`元素

一个表格可以使用`thead`，`tbody`，`tfoot`这三个元素来分成对应的三个部分，这样可以更好的组织数据。

`thead`包裹了表头元素，表示属于表格的头部，`thead`应该在`caption`元素和`tbody`之间。

紧跟着`thead`之后可以是`tbody`元素或者`tfoot`元素。之前`tfoot`元素需要紧跟在`thead`之后，这点在HTML5中已经被取消。现在只要有唯一的父元素，它们的顺序随意。而且，`tbody`元素需要包含表格中最重要的内容，`tfoot`元素则包含表格概述性的内容。

```html
<table>
  <caption>...</caption>
  <thead>
    ...
  </thead>
  <tbody>
    ...
  </tbody>
  <tfoot>
    ...
  </tfoot>
</table>
```

##表格边框

表格中的一个能够让数据更加易懂的[设计](http://dev.opera.com/articles/view/33-styling-tables/)组件便是边框。表格，行，列，或者独立单元格的边框可以对表格数据的理解和表格的快速浏览有着很大的影响。在CSS中定义边框样式的时候在此由两个属性需要使用`border-collapse`和`border-spacing`。

###`border-collapse`属性

表格由外面的`table`元素和`td`元素组成，同时对两者使用边框会使得边框叠加。譬如，在整个表格使用2px的边框，然后在单元格上再使用2px的边框，最终会使得边框便是4px。

`border-collapse`属性定义了表格边框的模式。`border-collapse`属性由三个值，包括：`collapse`，`separate`和`inherit`。默认值`separate`表示不同的边框会叠加起来，而`collapse`则表示不同的边框会合并起来，选用单元格作为主要的边框。

```css
table {
  border: 2px solid blue;
  border-collapse: separate;
}
th, td {
  border: 2px solid red;
}
```
<div class="code-box ">
    <h4><code>border-collapse</code>属性Demo</h4>
    <div class="post9-table-border">
        <div>
          <table class="separate">
            <thead>
              <tr>
                <th scope="col">Luke</th>
                <th scope="col">Brad</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>88</td>
                <td>76</td>
              </tr>
            </tbody>
          </table>
          <p><code>separate</code></p>
        </div>
        <div>
          <table class="collapse">
            <thead>
              <tr>
                <th scope="col">Luke</th>
                <th scope="col">Brad</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>88</td>
                <td>76</td>
              </tr>
            </tbody>
          </table>
          <p><code>collapse</code></p>
        </div>
    </div>
</div>

###`border-spacing`属性

`border-collapse`属性的`separate`值让表格的边框不重叠，而`border-spacing`属性则决定了两个边框的空间大小，在上述的例子中，如果再设置`border-spacing`属性为2px，那么也就创建了一个总共6px的边框。

```css
table {
  border: 2px solid blue;
  border-collapse: separate;
  border-spacing: 2px;
}
th, td {
  border: 2px solid red;
}
```

<div class="code-box">
<h4><code>border-spacing</code>属性Demo</h4>
<div class="post9--table-border-spacing">
	<table>
    <thead>
      <tr>
        <th scope="col">Luke</th>
        <th scope="col">Brad</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>88</td>
        <td>76</td>
      </tr>
    </tbody>
  </table>
</div>
</div>

###添加边框

为整个表格增加边框确实挺简单的，但是为行或者单元格增加边框就有点难度。下面是几个添加边框的例子，在此额外推荐的例子是来自Twitter的[tables within Bootstrap](http://twitter.github.com/bootstrap/base-css.html#tables)。

####行边框

为表格的行与行之间添加边框，可以通过为单元格添加底部的边框来实现，去除最后一行的边框只需使用伪类`last-child`来实现。

```css
table {
  border-collapse: collapse;
  border-spacing: 0;
}
th, td {
  border-bottom: 1px solid #c6c9cc;
}
tr:last-child td {
  border: 0;
}
```
<div class="code-box post9-table-border-row">
<h5>行边框Demo</h5>
<table>
    <thead>
      <tr>
        <th>Track</th>
        <th>Artist</th>
        <th>Length</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>We Are Young</td>
        <td>Fun.</td>
        <td>4:10</td>
      </tr>
      <tr>
        <td>Pumped Up Kicks</td>
        <td>Foster the People</td>
        <td>3:59</td>
      </tr>
      <tr>
        <td>Midnight City</td>
        <td>M83</td>
        <td>4:03</td>
      </tr>
    </tbody>
  </table>
</div>

####单元格边框

为单元格添加边框也很简单，只需为每一个单元格添加即可，只是还需要设置表格的边框为重叠。

```css
table {
  border-collapse: collapse;
  border-spacing: 0;
}
th, td {
  border: 1px solid #c6c9cc;
}
```
<div class="code-box post9-table">
<h5>单元格边框Demo</h5>
<table>
    <thead>
      <tr>
        <th>Track</th>
        <th>Artist</th>
        <th>Length</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>We Are Young</td>
        <td>Fun.</td>
        <td>4:10</td>
      </tr>
      <tr>
        <td>Pumped Up Kicks</td>
        <td>Foster the People</td>
        <td>3:59</td>
      </tr>
      <tr>
        <td>Midnight City</td>
        <td>M83</td>
        <td>4:03</td>
      </tr>
    </tbody>
  </table>
</div>

##文本的对齐

