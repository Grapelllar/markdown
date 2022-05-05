# HTML常用标签

## 1、<!--..--> 标签（comment 注解）

- 它不展现在浏览器，它有助于阅读代码
- JavaScript 注释示例如下，最后的两个反斜杠 // 将阻止 --> 执行。

<script type="text/javascript">
    <!--function displayMsg() {  
        alert("Hello World!")
    }
    //-->
</script> 

# 2、<a> 标签

- a 标签定义的是超链接 href ，如果没有定义 href 属性则只作为超链接的占位符，默认超链接显示在当前页面

- 默认情况下，超链接在浏览器中会显示如下样式：

  （1）未点击过的链接呈蓝色

  （2）已点击过的链接呈紫色

  （3）活跃的链接呈红色（点击后，页面正在转向新地址时）

- 例子

  （1）链接电话号码

  ````html
  <a href="tel:+4733378901">+47 333 78 901</a>
  ````

  （2）跳转到某一部分

  ````HTML
  <a href="#section2">Go to Section 2</a>
  ````

  （3）嵌入  JavaScript

  ````html
  <a href="javascript:alert('Hello World!');">Execute JavaScript</a>
  ````

  

# 3、<audio>标签

- audio 标签用于嵌入音频流，可以嵌入一个或多个 <source> 标签，浏览器会选择适配且靠前的。

- audio 标签中间夹杂的文档只会在不适配的时候显示于浏览器中

- 三种主流音频是 HTML 支持的 ：MP3、WAV、OGG（除 Safari ）

- 常用属性：

  （1）autoplay：当资源就绪时自动播放，类型是 Boolean（Chrome 等浏览器的高级版本已弃用）

  （2）controls：显示控制栏，包括开始、暂停、进度条、音量、倍速等，类型是 Boolean

  （3）loop：循环播放，类型是 Boolean

  （4）muted：载入时静音，类型是 Boolean

  （5）preload：设置预先加载方式（当启用 autoplay 时该属性自动失效），有三种：auto（全部加载）、							metadata（只载入元数据）、none（不预先载入）

  （6）src：指定资源位置

## 4、<body>标签

* HTML 的核心内容都在里面，一个 HTML 文件只能拥有一个 body

* 默认的 CSS 样式：

  ````css
  body {
    display: block;
    margin: 8px;
  }
  
  body:focus {
    outline: none;
  }
  ````



## 4、 br 标签

* br 代表一个新行，它是一个空标签，意味着它没有结束标签。

## 5、button 标签

* button 与 input 标签的区别：在 button 中可以放置文本 (and tags like `<i>`, `<b>`, `<strong>`, `<br>`, `<img>`, etc.). 但是 input 不行
* button 中尽量指明 type























```
<i>`, `<b>`, `<strong>`, `<br>`, `<img>
```