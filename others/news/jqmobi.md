---
layout: share
title: jQ.Mobi框架介绍
---
<h1 class="post-title">jQ.Mobi框架介绍</h1>
<p class="meta">2013/04/13</p>
[jQ.Mobi](http://www.jqmobi.com/)是基于HTML5重写的jQuery框架，由appMobi开发并且开源托管于github，在此有简易的[在线文档](http://app-framework-software.intel.com/documentation.php)提供查阅。
jQ.Mobi相比于其他方案具有体积小速度快的优势。

![code size](images/2013/04/jqmobi-01.jpg)

![JavaScript Engine Speed](images/2013/04/jqmobi-02.jpg)


jQ.Mobi由三个组件组成：

-	查询（query）程序库
-	jQ.ui——为webkit内核浏览器提供的用户界面程序库
-	jQ.Plugin——针对webkit浏览器的插件支持

下面主要讲解下框架的UI部分。

##1 基本页面布局

![基本页面布局](images/2013/04/jqmobi-03.jpg)

上图即为jQ.mobi提供的基本布局，从视觉上分为三个部分**头部、内容区域、底部**，如下图。

![基本页面布局三个部分](images/2013/04/jqmobi-04.jpg)

依照苹果App界面设计规则：

-	header头部属于**导航栏固定于整个应用的顶部**，主要是“你在这里”的标志（也可承载按钮）。
-	content内容区则用于**承载应用的不同页面**。
-	footer底部区则属于**标签栏固定于整个应用的底部**，用户可以通过点击不同的标签到达不同的页面。

应用的导航栏和标签栏，通常都是固定页面的顶部和底部，对于web app的布局中由于ios浏览器对于CSS的position:fixed支持很不好，因此**通用的解决方案（包括jQ.mobi)都是使用绝对定位position:absolute。**

对于jQ.mobi框架来说对应三部分的HTML代码为:

```html
<div id="jQUi">
  <div id="header"></div>
  <div id="content">
    <div class="panel"></div>
    <div class="panel"></div>
  </div>
  <div id="navbar"></div>
</div>
```

##2.jQ.Mobi中四种导航模型及其基本的HTML结构

苹果app定义了三种典型的导航模式再加上现在广为使用的“抽屉式”导航，四种导航模型在App设计中大量使用也覆盖了大部分应用的需求。

###2.1 标签栏导航模型

上面的图示则是典型的标签栏导航，也是目前最为欢迎的导航模型。

![标签栏](images/2013/04/jqmobi-05.jpg)

标签栏固定于应用的底部，点击其中不同的标签即可在不同的页面中切换，这种导航方式**适用于不同页面形式不一的复杂的应用。**
在jQ.Mobi中对应的HMTL代码为：

```html
<div id="navbar">
	<a href="#"></a>
	<a href="#"></a>
	<a href="#"></a>
	<a href="#"></a>
	<a href="#"></a>
</div>
```

受限于手机屏幕分辨率，标签栏中标签最好不要超过5个，如果标签数量超过5个，每个标签宽度过小，很可发生标签不易点中的问题，影响体验。
而如果页面归类超过5个，建议的处理方案是**将最后一个标签作为扩展标签设为更多。**

需要提示的是在jQ.Mobi框架中应用的所有页面都在一个HTML文档中，因此标签栏导航模式中页面切换实际上属于锚点切换，其不同页面的基本HTML代码为：

```html
<div id="content">
	<div class="panel"></div>
	<div class="panel"></div>
	<div class="panel"></div>
        …
</div>
```

**不同的页面包含在不同的class为panel的`div`中。**

###2.2 树形结构导航模型

![树形结构导航](images/2013/04/jqmobi-06.jpg)

上图即为典型的树形结构导航模型，树形结构适用于有大量分类项目的页面，其实际为大量的列表项。对应的HTML代码为：

```html
<ul>
  <li> </li>
  <li> </li>
  <li> </li>
  …
</ul>
```

###2.3 平铺页面导航模型

![平铺页面导航](images/2013/04/jqmobi-07.jpg)


上图即为平铺页面导航模型的基本结构，平铺页面导航模型的应用中最为经典的例子便是iphone中自带的天气应用，通常**此种模型使用较为简单的应用，功能较为单一且没有滚屏。**

在jQ.Mobi框架中可以使carousel插件实现，其HTML代码也较为简单：

```html
 <div id="carousel">
      <div> </div>
      <div> </div>
      <div> </div>
      …
 </div>
```

2.4 “抽屉式”导航模型

![“抽屉式”导航](images/2013/04/jqmobi-08.jpg)


上图为“抽屉式”导航模型的基本结构，抽屉式导航最为典型的应用为私密社交应用path，此种导航的核心思想为”隐藏“，更加能突出应用的核型功能，而将其他次要的功能页面（譬如设置页面）路径隐藏。**此种导航模型使用核心功能单一，不户无需频繁切换页面的应用。**
在jQ.Mobi框架中使用此类导航也十分的方面，其HTML代码为：

```html
 <div id="jQUi">
      <div id="header" class="haMenu"></div>
      <div id="content" class="haMenu" >
           <div class="panel"></div>
           <div class="panel"></div>
           …
      </div>
      <div id="navbar" class="haMenu"></div>
      <div id="menu"></div>
 </div>
```

而对于实际的应用可以看出大多数的应用并不是使用单一的导航模型，而是各种导航模型混用，至于**选择那种导航模型作为主导航，则需根据应用的功能，使用场景以及用户群体等因素综合考虑。**

##3 jQ.Mobi框架细节

###3.1 框架基本布局

之前提到过jQ.Mobi框架的页面都在一个HTML的文档中，除去导航栏（#header）和标签栏（#navbar）之外的内容页面都存在id为content的`div`当中，三者都是绝对定位。

其HTML和对应的CSS为：

```html
<!---HTML code--->
<div id="jQUi">
 	<div id="header"></div>
 	<div id="content"></div>
 	<div id="navbar"></div>
</div>
```

```css
/*---CSS code---*/
#header {
 	height : 48px;
}

#content {
 	position:absolute;
 	top:48px;
 	bottom:62px;
 	left:0;
 	right:0;
 	z-index:180;
}

#navbar {
 	position:absolute;
 	bottom:0;
 	left:0;
 	right:0;
 	height:62px;
 	z-index:1000;
}
```

上面的即是框架最基本的布局方式，#header，#navbar固定在屏幕的上下边，相应#content的盒子占据了其他区域。值得注意的是#navbar的z-index远高于#content的z-index。

###3.2 框架页面切换

框架的切换页面都包裹在class为panel的`div`中。

```html
<div id="content">
 	<div id="page1" class="panel" title=“xxx" selected="true"></div>
 	<div id="page2"class="panel" title=“xxx"></div>
 	<div id="page3"  class="panel" title=“xxx"></div>
</div>

<div id="navbar">
 	<a href="#page1">XXX</a>
 	<a href="#page2">XXX</a>
 	<a href="#page3">XXX</a>
</div>
```

```css
/*---panel style---*/

.panel {
 	display:none;
 	position:absolute;
 	width:100%;
 	height:100%;
 	top:0;
 	left:0;
 	z-index:180;
}
```

切换页面都在同一个HTML文档中，panel页面默认设置为隐藏（display:none）**使用锚链接跳转，跳转的同时需要显示页面的`display`属性设为block，同时给需要隐藏的页面一个向左移动的动画，加之panel页面使用绝对定位，宽度高度均铺满content，这样的跳转就达到了native应用页面切换的效果。**


而在页面切换时，另外的动作就是将panel页面中已经定义的`title`属性中的值显示到导航中，并根据jQ.Mobi定义的属性`data-tab`的值来选中标签栏对应的标签。

###3.3 panel属性介绍

正如前面所言应用的切换页面都包裹在class为panel的`div`中，因此jQ.Mobi预先定义了多个属性来应对不同的需求。

-	**selected="true"** 当panel设置此属性后，在应用打开之后默认加载该页面。
-	**modal="true"** 将panel转变为模态视图，框架中[模态视图](http://www.guimobile.net/ios-hig/8.3.3.html)默认铺满整个屏幕（可在CSS中更改）。
-	**data-header="id"** 设置之后，在切换到该panel的时候将会加载对应id的自定义`header`标签。
-	**data-footer="id"** 设置之后，在切换到该panel的时候将会加载对应id的自定义`footer`标签。
-	**data-nav="id"** 设置之后，在切换到该panel的时候将会加载对应id的自定义`nav`标签。
-	**data-defer="filename.html"** 设置此属性之后该panel会加载远程的页面或者url。若想将内容分属到不同的文件，该属性会很有用。在所有的文件都异步加载之后jq.ui.ready才会起作用。
-	**data-tab="anchor_id"** 正如之前提到的，设置该属性之后，在panel加载的时候将标签栏中对应标签选中。而当你通过js而不是单击标签栏的标签来加载panel的时候此属性同样有用。
-	**data-load="func_name"** 设置之后，panel加载之后会运行该名称的js函数。`div`作为一个参数传递，因此你可以使用一个函数来是的其他的属性起作用。
-	**data-unload="func_name"** 与data-load相似，只是在页面关闭的时候才运行js函数。
-	**CSS属性 overflow:hidden** 设置之后，会禁止panel页面的自动滚动。当panel页面需要自动扩展的时候该设置很有用处，例如之前提到Carousel应用或者地图类应用。

jQ.Mobi允许你自定义属性，更为详细的介绍可以查看其[在线文档](http://app-framework-software.intel.com/documentation.php#jqUi/jqui_panels)。

###3.4 panel页面滚动实现方式。

因为ios5之前版本的webview原生不支持浏览器滚动，因此对于panel页面的滚动就不能靠CSS中的overflow属性来实现了。

目前的**滚动替代方案基本是靠CSS动画来实现**，jQ.Mobi中使用3D动画来实现，因为**[3D动画能够使用浏览器的硬件加速](http://blog.teamtreehouse.com/increase-your-sites-performance-with-hardware-accelerated-css)**，可以让滚动更加流畅，效果也直逼native应用。

框架在panel页面允许滚动的情况下，将panel作为滚动的**容器（container）**，然后将panel元素的所有子元素**content**，再包裹一个`div`标签作为**viewport**，在这一层上面使用3D transform中的translate3d属性来达到滚动的效果，具体通过改变translate3d的Y值也就是纵轴的值来实现滚动。

```css
/*--对应的css写法---*/
transform: translate3d(0, 100px, 0);
```

![滚动实例图](images/2013/04/jqmobi-08.png)
![滚动关键CSS代码](images/2013/04/jqmobi-09.png)







