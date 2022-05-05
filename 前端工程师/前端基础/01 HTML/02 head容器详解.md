# head 容器详解（包括title、style、base、link、mate、script、noscript七大内置标签）

[TOC]

## 一、head标签

* head 标签是存放元数据（metadata，data about data）的数据，即解释数据的数据。
* 元数据一般不直接展示给用户。
* 元数据内定义标题 title（每个 HTML 都必须要有）、作者、更新时间、样式链接等。
* \<head\> 标签中可以含有 <title\>、 <style\>、  <base\>、 <link\>、  <mate\>、 <script\>、 <noscript\>  七种标签。

## 二、head容器下的标签

### 1、 \<title\> 标签：

* title 是 HTML 中的必备元素，同时只能被定义一次，若多次定义只取第一次定义的。

* title 标签需要是纯文本的，它会展示在网页的选项卡中。
* 当用户进行收藏操作时，title 提供收藏标题。
* SEO（search engine optimization） 是根据 title 进行搜索的，影响搜索算法的结果，因此 title 内容很重要，不能过短，也不能超过 50-60 个单词，超过部分可能被截取不显示。

### 2、\<style\> 标签：

* 用于定义文档的样式，显示于浏览器中。

* 当对一个元素重复定义了相同的样式，会自动选择最后一个样式进行渲染。

* style 中有两个属性：

  1）media ：指定哪种设备显示该样式 ```=》 媒体查询待深入研究```

  2）type：默认是 “text/css”，代表指定样式为 CSS，同样还有等进行指定 

### 3、\<base\> 标签：

* 定义文档中所有相对路径的根路径，以及指定链接的跳转方式（此说法其实不够准确，和框架有关） ```=》待深入研究```

* 拥有两个属性，必须含有 href 和 target 中的一者。

*  target  中拥有四种值 ```=》待深入研究```

  1）_blank : 在当前窗口打开，不跳转

  2）_self ：默认在当前窗口打开，不跳转

  3）_parent ： Opens the link in the parent frame

  4）_top： Opens the link in the full body of the window

### 4、\<link\>标签：

* 该标签链接外部资源，并定义了和外部资源的关系。
* 大多数用于链接外部样式表和添加网站图标（ Favicon设计网站：[https://www.favicon.cc](https://www.favicon.cc/)）
* 它包含 href 、media ```=》 媒体查询待深入研究``` rel （指定与链接文件的关系，属性有 icon、stylesheet 等）

### 5、\<mate\>标签：

* mate 标签存放的是元数据，指明关键词（供浏览器搜索）、作者、详情、刷新时间**视图效果**等信息

* 元数据不会展示出来，但是会被解析

* 几个例子：

  1）为搜索引擎定义关键词

  <meta name="keywords" content="HTML, CSS, JavaScript">

  2）定义 30 秒刷新一次

  <meta http-equiv="refresh" content="30">

  3）设置 viewport 使网页显示效果在设备上显示得更佳

  <meta http-equiv="refresh" content="30">

* **设置 viewport** （详细介绍：https://www.w3schools.com/css/css_rwd_viewport.asp） ```=》待深入研究```

  这个属性告诉浏览器如何控制页面尺寸以及缩放

  设定宽度以适配设备宽度：```width=device-width```

  设定初始缩放级别 ：````initial-scale=1.0````

  <meta name="viewport" content="width=device-width, initial-scale=1.0">

### 6、\<script\>标签：

* 用于嵌入 JavaScript 脚本
* 可以指定 scr 指向外部脚本文件

### 7、\<noscript\>标签：

* 当浏览器不支持 script 时，将显示该标签的内容

补充：lang 标签

学习网站：https://www.w3schools.com/