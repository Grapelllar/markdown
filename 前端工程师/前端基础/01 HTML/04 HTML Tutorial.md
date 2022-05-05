# HTML 入门教程（Tutorial）

- HTML是超文本标记语言（ Hyper Text Markup Language ）
- 有些 HTML 元素没有内容，比如 br，没有结束标签，这种称为空元素
- HTML 页面结构

![HTML Page Structure](D:\NEW\Study\markdown\pic\前端基础\HTML Page Structure.png)

* HTML 的历史

![image-20220410203040475](C:\Users\15364\AppData\Roaming\Typora\typora-user-images\image-20220410203040475.png)

## HTML Basic

* HTML 文档需要开始于 <!DOCTYPE html>，它代表文档的类型，能使得浏览器正确地转换文档，它需要在 <html> 标签前出现且只能出现一次。对于 html 5，Doctype为 <!DOCTYPE html>
* HTML 文档在 <html></html> 间
* 可见元素在 <body></body> 间
* HTML 的标题有五级，为 <h1> - <h6>
* \<p\> 标签定义一个段落

* <a> 标签定义超链接，用 href 元素定义链接网站
* <img> 为图片标签，资源地址在 src 中定义

## HTML 元素（HTML Elements）

* HTML 的一个元素使用开始标签和结束标签来定义的，但有的是空元素，如 \<br\> ，它代表换行，没有内容并且没有结束元素，例如：

  ````html
  <p>This is a <br> paragraph with a line break.</p>
  ````

* HTML 元素可以被嵌入，即一个元素中可以包含另一个元素

* 在编写 HTML 文档时候，不要忘记加上结束标签，有可能会出现问题（在 XHTML 中严格要求有结束标签）
* 在编写 HTML 文档的时候，标签的大小写不敏感，但尽量小写，在 XHTML 中严格要求小写

## HTML 属性（HTML Attributes）

* HTML 属性一般定义于起始标签

* HTML 属性一般以键值对的形式出现，如 name = "value"

* href 用于指定超链接跳转的 URL，而 src 指定的是如图片的根目录，可以使用绝对路径和相对路径

* 绝对路径和相对路径

  （1）绝对路径：常用于不在当前网页作用域中，如下定义。但使用其他网站的图片，若其他网站改动，有可能导致自己网页的图片失效。

  ````html
  src="https://www.w3schools.com/images/img_girl.jpg".
  ````

  （2）相对路径：推荐，当图片位于当前网站时。当未加斜杆时代表作用域在当前目录，加后则返回上一级。

  ````html
  src="/images/img_girl.jpg".

* 在定义 <html> 标签时，可以定义 lang 属性来确定使用的语言和国家（前两个字母为语言，后两个为国家），例如（英语-英国）：

  ````html
  <!DOCTYPE html>
  <html lang="en-US">
  <body>
  ...
  </body>
  </html>
  ````

* title 属性定义元素的额外信息，当鼠标略过时显示在小窗口中

* 属性大小写不敏感，但在 XHTML 中严格小写

* 属性值不要求一定要使用引号，但建议引用，在 XHTML 中严格要求引用

* 属性中的引号可以是单引号或是双引号。但如果内容是单/双引号，则必须相对应地使用双/单引号

  ```html
  <p title='John "ShotGun" Nelson'></p>
  <p title="John 'ShotGun' Nelson"></p>
  ```

## HTML 标题（HTML Headings）

* 标题有 <h1> - <h6> 六种，由大到小
* 浏览器会自动为每个标题后添加一些空格（即边距margin）
* 搜索引擎会根据标题来检索网页结构和内容，同样用户也是从标题浏览文章的大致内容，因此标题很重要
* 请将标题元素只用于显示标题中，而不要使用标题元素进行加粗。
* 标题大小可以通过 style 中修改 font-size 来实现。

## HTML 段落（HTML Paragraphs）

* HTML 中使用 <p> 标签定义一个段落，浏览器会自动为每个段落后面加一些空格（即边距margin）
* 在不同大小的屏幕、缩放中，仅靠 HTML 我们并不能确定显示出来的样式
* \<p\> 中的多个空格和换行将被自动忽略，无法通过添加空格来改变显示样式（只能添加一个空格）
* \<hr\> 标签（Horizontal Rules）用作水平分割线来分离网页中的内容，它是一个空元素
* \<br\> 标签定义一个新行
* \<pre\> 标签（preformatted text）为预编排文本，可以用于添加诗句等（可以任意添加换行和空格）

## HTML Styles (HTML Styles)

* 语法如下，属性是 CSS 属性，值是 CSS 的值，属性与属性中间添加封号，属性与值中间为英文冒号

  ````html
  <tagname style="property:value;">
  ````

* 常用属性枚举：

  （1）background-color 背景颜色

  （2）color 设置文本颜色

  （3）font-family 定义哪种字体（若库中没有将使用默认字体）

  （4）font-size 字体大小

  （5）text-align 对齐方式

  

## HTML 文本格式化（HTML Text Formatting)

* 常用特殊格式

  （1）<b> Bold text 加粗

  （2）<strong> Important text 重要并加粗

  （3）<i> Italic text 斜体

  （4）<em> Emphasized text 强调，斜体

  （5）<mark> Marked text 黄色高亮

  （6）<small> Smaller text 小文本

  （7）<del> Deleted text 带有删除横杆的文本

  （8）<ins> Inserted text 带有下划线的插入文本

  （9）<sub> Subscript text 下标

  （10）<sup> Superscript text 上标

## HTML 引号和引文元素（HTML Quotation and Citation Elements）

* 常用元素

  （1）<blockquote> 引用块，表示一个片段来源于引用资源，显示时会被缩进，属性 cite 定义链接 URL

  （2）<q> short quotations，会插入英文引号

  （3）<abbr> abbreviation or an acronym，即缩写或首字母缩略词，当鼠标掠过时会小窗口显示 title 原意，这个标签对于搜索引擎有帮助

  ![abbr](D:\NEW\Study\markdown\pic\前端基础\abbr.png)

  （4）<address> 嵌入邮箱、地址、电话等，显示时会斜体并且上下各空一行

  （5）<cite> 引用，斜体显示，比如一本书名、一首歌、一部电影的名字，这些带有创造性的名字用这个来定义，斜体显示

  （6）<bdo> Bi-Directional Override，正序/反序覆写当前文本。属性 dir = "rtl" 为反序，ltr 为正序

## HTML 注释（HTML Comments）

* 语法为：<!-- -->，可以使用注释来寻找错误在哪一行（控制变量法）

* 多行注释需要包裹，如：

  ```html
  <p>This is a paragraph.</p>
  <!--
  <p>Look at this cool image:</p>
  <img border="0" src="pic_trulli.jpg" alt="Trulli">
  -->
  <p>This is a paragraph too.</p>
  ```

* 可以放在内容中，如：

  ```html
  <p>This <!-- great text --> is a paragraph.</p>
  ```

## HTML 颜色（HTML Colors）

* 支持预定义的 RGB, HEX, HSL, RGBA, or HSLA

  ![htmlColors](D:\NEW\Study\markdown\pic\前端基础\htmlColors.png)

* 支持 140 种语义化颜色，详见 https://www.w3schools.com/colors/colors_names.asp

* RGB、HEX、HSL 快速寻色网站（实用）：https://www.w3schools.com/html/html_colors_rgb.asp ``` ==》待深入研究```

## HTML CSS

* CSS（Cascading Style Sheets） 代表层叠（级联）样式表。之所以叫 Cascading  是因为子元素自动继承父元素样式（如 p 标签样式自动继承 html 标签样式），除非子元素重写自己的样式

* 在 HTML 中添加 CSS 的三种方法

  （1）内联（Inline）：在单个元素中使用 style

  （2）内部（Internal）：在头部使用 style，单页应用

  （3）外部（External）：定义于 CSS 文件当中，在需要使用的页面的 link 中链接

* border、padding、margin：

  （1）border 为元素的边界

  （2）padding 为 border 到 margin 间的填充

  （3）margin 为 border 外界

## HTML Links（HTML 链接）

* 当移动到一个链接的时候，鼠标会变成小手指

* link 主要通过 a 标签，语法如下：

  ```html
  <a href="url">link text</a>
  ```

* 默认情况下，超链接在浏览器中会显示如下样式：

  （1）未点击过的链接呈蓝色

  （2）已点击过的链接呈紫色

  （3）活跃的链接呈红色（点击后，页面正在转向新地址时）

  同样，也可以改变它们的样式，例子如下：

  覆写则需要覆写以下全部伪类属性，否则默认其他伪类不生效。其中，:link 为未点击，visited 为已点击，hover 为鼠标掠过，active 为生效中。

  ```html
  <style>
  a:link {
    color: green;
    background-color: transparent;
    text-decoration: none;
  }
  
  a:visited {
    color: pink;
    background-color: transparent;
    text-decoration: none;
  }
  
  a:hover {
    color: red;
    background-color: transparent;
    text-decoration: underline;
  }
  
  a:active {
    color: yellow;
    background-color: transparent;
    text-decoration: underline;
  }
  </style>
  ```

* target 属性定义页面如何跳转，默认是在当前窗口呈现

  （1）_blank : 在当前窗口打开，不跳转

  （2）_self ：默认在当前窗口打开，不跳转

  （3）_parent ： Opens the link in the parent frame

  （4）_top： Opens the link in the full body of the window

* 其他元素也同样可以使用跳转，只需包裹在 a 标签中即可，例子如下：

  ````html
  <a href="default.asp">
  <img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;">
  </a>
  ````

* 链接到邮件地址：

  ````html
  <a href="mailto:someone@example.com">Send email</a>
  ````

* 按钮链接：

  ````html
  <button onclick="document.location='default.asp'">HTML Tutorial</button>
  ````

* 可以设置 title 属性，在鼠标掠过时显示小窗口

* 可以用作 bookmark 使用进行跳转，以元素的 id 为索引跳转，例如：

  ````html
  <h2 id="C4">Chapter 4</h2>
  <a href="#C4">Jump to Chapter 4</a>
  <!-- 在其他页面跳转 -->
  <a href="html_demo.html#C4">Jump to Chapter 4</a>
  ````

## HTML 图片（HTML Images）

* 实际上，图片并没有嵌入网页中，img 标签是预留了一个空间给图片，图片是以链接的方式载入的

* img 是空标签，它只有属性，没有结束标签

* img 中包含两个必要的属性，src 和 alt（alt 即 alternate ，其中的内容是图片加载失败的时候显示的文字）：

  ```html
  <img src="url" alt="alternatetext">
  ```

* 指定图片大小是必要的，不指定可能导致网页图片闪动。否则可以通过 style 属性和直接定义 width 和 height 属性来修改图片大小，但建议使用 style，因为样式表中可能会有 style，而元素的属性并不能覆写样式表，样式表是优先显示的，因此会导致修改单个元素的大小时失效。例子：

  ````html
  <!DOCTYPE html>
  <html>
  <head>
  <style>
  img {
    width: 100%;
  }
  </style>
  </head>
  <body>
  
  <img src="html5.gif" alt="HTML5 Icon" width="128" height="128">
  
  <img src="html5.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
  
  </body>
  </html>
  ````

* 支持显示 gif 动图以及以下的格式

![imgeFormats](D:\NEW\Study\markdown\pic\前端基础\imgeFormats.png)

* 支持包裹在 a 标签中进行超链接

* 可以通过 css 的 float 属性设置左右浮动，例子如下：

  ````html
  <!-- 图片显示在文字的右边 -->
  <p><img src="smiley.gif" alt="Smiley face" style="float:right;width:42px;height:42px;">
  The image will float to the right of the text.</p>
  
  <!-- 图片显示在文字的左边 -->
  <p><img src="smiley.gif" alt="Smiley face" style="float:left;width:42px;height:42px;">
  The image will float to the left of the text.</p>
  ````

## HTML 图标（HTML Favicon)

* 使用在线工具制作网页图标：[https://www.favicon.cc](https://www.favicon.cc/)

* 显示在浏览器标签中的最左侧，一般重命名为 favicon.ico，例子如下：

  ````html
  <head>
    <title>My Page Title</title>
    <link rel="icon" type="image/x-icon" href="/images/favicon.ico">
  </head>
  ````

## HTML 表格（HTML Table）

* 基本标签：

  （1）tr：tablerow，表中的行，<th>、<td> 标签应放置在这里面

  （2）th：tableheadercell，表头单元格，默认会加粗并居中

  （3）td：tabledatacell，表中的数据单元

  （4）table : 所有以上标签包裹在 table 标签中

* 例子：

  ```html
  <table>
    <tr>
      <th>Company</th>
      <th>Contact</th>
      <th>Country</th>
    </tr>
    <tr>
      <td>Alfreds Futterkiste</td>
      <td>Maria Anders</td>
      <td>Germany</td>
    </tr>
    <tr>
      <td>Centro comercial Moctezuma</td>
      <td>Francisco Chang</td>
      <td>Mexico</td>
    </tr>
  </table>
  ```

## HTML 列表（HTML Lists）

* 列表分为三种，<ul> （Unordered List，未排序的列表，每一项前为实心圆点）和、<ol>（Ordered List，已排序的列表，如1.2.3.）和自定义列表。有序列表和无序列表列表中的每一项使用 <li> 标签，li 标签可以包含图片、链接等其他 HTML 元素

* 无序列表，可以通过修改 style 中的 list-style-type 属性修改 list 前面的 marker，有以下几种值：

  （1）dis 默认的实心圆

  （2）circle 空心圆

  （3）square 实心正方形

  （4）none 无标记

  同样可以在无序列表中嵌入无序列表，当嵌入时每一个 ul 的marker 按照以下顺序标记：

  dis -> circle -> square -> square -> ... -> square

  有序列表同样可以使用嵌套。当有序列表嵌套无序列表时，无序列表的 marker 层级关系同上。

  样例如下：

  ```html
  <!DOCTYPE html>
  <html>
  <body>
      <h2>A Nested List</h2>
      <p>Lists can be nested (list inside list):</p>
      <ul>
          <li>Coffee</li>
          <li>Tea
              <ul>
                  <li>Black tea</li>
                  <li>Green tea</li>
                  <ul>
                      <li>Black tea</li>
                      <li>Green tea</li>
                      <ul>
                          <li>Black tea</li>
                          <li>Green tea</li>
                      </ul>
                  </ul>
              </ul>
          </li>
          <li>Milk</li>
      </ul>
  
  </body>
  </html>
  ```

  效果图如下：

  ![nested-ul](D:\NEW\Study\markdown\pic\前端基础\nested-ul.png)

  通过 float:left 将无序标题设置为导航栏：```==》待深入研究```

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <style>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #333333;
  }
  
  li {
    float: left;
  }
  
  li a {
    display: block;
    color: white;
    text-align: center;
    padding: 16px;
    text-decoration: none;
  }
  
  li a:hover {
    background-color: #111111;
  }
  </style>
  </head>
  <body>
  
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#news">News</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#about">About</a></li>
  </ul>
  
  </body>
  </html>
  ```

  效果如下：

  ![navigationMenu](D:\NEW\Study\markdown\pic\前端基础\navigationMenu.png)

* 有序列表中，可以通过修改 type 属性来指定每个 list 的 marker

  （1）type = "1" 默认样式，1. 开始
  
  （2）type = "A"，大写字母（超过 26 个字母以 AA 、AB 显示，以此类推）
  
  （3）type = "a"，小写字母
  
  （4）type = "I"，英文大写 I ，罗马大写数字
  
  （5）type = "i"，英文小写的 i，罗马小写数字
  
* 有序列表中，可以修改 start 属性来指定起始标号

* 自定义列表中，使用 <dl> （Description Lists）包裹，使用 <dt> （term）标签表示每一项的名称，<dd> （description）标签描述每一项。效果如下：

  ````html
  <!DOCTYPE html>
  <html>
  <body>
  
  <h2>A Description List</h2>
  
  <dl>
    <dt>Coffee</dt>
    <dd>- black hot drink</dd>
    <dt>Milk</dt>
    <dd>- white cold drink</dd>
  </dl>
  
  </body>
  </html>
  ````

  ![dl](D:\NEW\Study\markdown\pic\前端基础\dl.png)

## HTML 块和内联元素（HTML Block and Inline Elements）

* 块级元素起始于新行，并且会自动地在前后添加一些空白（即margin值），块级元素总是会尽可能地占满所有宽度，最常见的块级标签有 <p> 、<div>，所有的块级元素如下：

  ![block-levelTag](D:\NEW\Study\markdown\pic\前端基础\block-levelTag.png)

* 内联元素在同一行中，它只占据必要的宽度，用于在一段文字中标记特定文字，如 <span>，**注意，内联元素不能包含块级元素**！所有的内联元素如下：

  ![inline-levelTag](D:\NEW\Study\markdown\pic\前端基础\inline-levelTag.png)

## HTML 类（HTML classes）

* 多个 HTML 元素可以使用同样的 class，常用于方便被 css 和 JavaScript 使用，class 属性可以被用在 HTML 中的所有元素中，类名大小写敏感

* 在 css 中，调用 class 属性用句点 + 类名

* 一个元素可以指定多个 class，会被应用所有 class 的样式。当指定的 class 样式具有相同属性但值不同时，默认覆写最后一个 class 的样式。

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <style>
  .city {
    background-color: tomato;
    color: white;
    padding: 10px;
  } 
  
  .main {
    text-align: center;
    color: yellow;
  }
  </style>
  </head>
  <body>
  
  <h2>Multiple Classes</h2>
  <p>Here, all three h2 elements belongs to the "city" class. In addition, London also belongs to the "main" class, which center-aligns the text.</p>
  
  <h2 class="city main">London</h2>
  <h2 class="city">Paris</h2>
  <h2 class="city">Tokyo</h2>
  
  </body>
  </html>
  
  ```

* id 属性可以用于设置书签（bookmark）进行跳转操作，如：

  ```html
  <a href="html_demo.html#C4">Jump to Chapter 4</a>
  ```

  

## HTML 唯一标识号(HTML Id)

* 一个元素只能拥有一个 Id，并且不能重复，```=》好像不是这样，有待深入研究```用于设置特定元素的样式（用 # 号标识）或操纵特定元素
* id 的值大小写敏感，不可以以数字开头、不可以添加空格。

## HTML 内嵌框架（HTML Iframes）

* 内嵌框架（Inline Frame），用于在网页中嵌入网页，如下套娃：<img src="D:\NEW\Study\markdown\pic\前端基础\htmlIframe.png" alt="htmlIframe" style="zoom:50%;" />

* 语法如下，在 iframe 中使用 title 可以让屏幕阅读器阅读title ：

  ````html
  <iframe src="url" title="description"></iframe>
  ````

* 可以使用 width 和 height 属性设置高低样式，或者使用 style 进行设置

* 可以设置  ````style="border:none;"```` 来移除 iframe 的边框。

  移除前：

  ![beforeRemove](D:\NEW\Study\markdown\pic\前端基础\beforeRemove.png)

  移除后：

  ![afterRemove](D:\NEW\Study\markdown\pic\前端基础\afterRemove.png)

* **Iframe 可以使用 target 属性来改变页面链接的内容**，例子如下，先是使用 iframe 定义了默认的链接，再在 a 标签内使用 target 设置点击连接后 iframe 跳转的链接：

  ```html
  <!DOCTYPE html>
  <html>
  <body>
  
  <h2>Iframe - Target for a Link</h2>
  
  <iframe src="demo_iframe.htm" name="iframe_a" height="300px" width="100%" title="Iframe Example"></iframe>
  
  <p><a href="https://www.w3schools.com" target="iframe_a">W3Schools.com</a></p>
  
  <p>When the target attribute of a link matches the name of an iframe, the link will open in the iframe.</p>
  
  </body>
  </html>
  ```

## HTML 脚本（HTML JavaScript）

* JavaScript 使网页具有动态性和交互性。

* \<script\> 标签用于定义客户端脚本（client-side script），要么内含脚本语句，要么通过 src 指向外部文件

* 选择一个 HTML 元素，在 JavaScript 常用 document.getElementById() 方法，下面的例子是在 HTML 中点击覆写文字的例子：

  ```html
  <!DOCTYPE html>
  <html>
  <body>
  
  <h1>My First JavaScript</h1>
  
  <p>JavaScript can change the content of an HTML element:</p>
  
  <button type="button" onclick="myFunction()">Click Me!</button>
  
  <p id="demo">This is a demonstration.</p>
  
  <script>
  function myFunction() { 
    document.getElementById("demo").innerHTML = "Hello JavaScript!";
  }
  </script>
  
  </body>
  </html>
  ```

* 选择 HTML 元素，覆写样式，注意原来有连号符的属性改为驼峰命名法，如 font-size 改为 fontSize，后面的值加双引号。

  ```javascript
  document.getElementById("demo").style.fontSize = "25px";
  document.getElementById("demo").style.color = "red";
  document.getElementById("demo").style.backgroundColor = "yellow";
  ```

* 使用 JavaScript 控制图片变化-灯光样例

  ```html
  <!DOCTYPE html>
  <html>
  <body>
  
  <h1>My First JavaScript</h1>
  <p>Here, a JavaScript changes the value of the src (source) attribute of an image.</p>
  
  <script>
  function light(sw) {
    var pic;
    if (sw == 0) {
      pic = "pic_bulboff.gif"
    } else {
      pic = "pic_bulbon.gif"
    }
    document.getElementById('myImage').src = pic;
  }
  </script>
  
  <img id="myImage" src="pic_bulboff.gif" width="100" height="180">
  
  <p>
  <button type="button" onclick="light(1)">Light On</button>
  <button type="button" onclick="light(0)">Light Off</button>
  </p>
  
  </body>
  </html>
  ```

* \<noscript\> 标签设置当浏览器禁用 JavaScript 时的显示

  ```javascript
  <noscript>Sorry, your browser does not support JavaScript!</noscript>
  ```

## HTML 文件路径（HTML File Paths）

* 与 Linux 的相对路径、绝对路径基本一致，开头为 / 进入根目录，.. 表示上一级目录，不加则表示从当前目录级出发，最好使用相对路径，以下都是相对路径（注意，/ 在这里为网页的根目录，因此是相对路径）：

  ![htmlFilePaths](D:\NEW\Study\markdown\pic\前端基础\htmlFilePaths.png)

## HTML 头部（HTML Head）

* HTML <head> 头部包括 <title>、<style>、<mate>、<link>、<script>、<base>、<noscript>七个标签。

  ```=》待深入研究，详见写过的文章```

## HTML 布局元素和技术（HTML Layout Elements and Techniques）

* 布局常用到一些语义化元素，如下：![layoutSemanticElements](D:\NEW\Study\markdown\pic\前端基础\layoutSemanticElements.png)

* 布局相关技术：framework（如 bootstrap）、float、flexbox、grid ```=》待深入学习```

## HTML 响应式设计（HTML Responsive Web Design）

* 响应式设计是为了让网页在各种设备都能美观，它将在不同设备自动调整尺寸，使用响应式布局前应加上：

  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```

  效果对比图如下：

  ![metaResponsive](D:\NEW\Study\markdown\pic\前端基础\metaResponsive.png)

* 响应式图片：使用 width:100px 时，图片大小会响应式缩小或增大，但可能会放大到超过它本身的大小，这样并不好看。因此会使用 max-width 属性解决这一问题，设定最大宽度，则响应式变化不会超过这一宽度。

* \<picture\> 标签可以使当浏览器视窗大小不同时，显示不同的图片，例子如下，**其中，max-width:600px 指当视窗小于等于 600px 时显示 smallflower。**

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body>
  
  <h2>Show Different Images Depending on Browser Width</h2>
  <p>Resize the browser width and the image will change at 600px and 1500px.</p>
  
  <picture>
    <source srcset="img_smallflower.jpg" media="(max-width: 600px)">
    <source srcset="img_flowers.jpg" media="(max-width: 1500px)">
    <source srcset="flowers.jpg">
    <img src="img_flowers.jpg" alt="Flowers" style="width:auto;">
  </picture>
  </body>
  </html>
  ```

* 文本大小可以使用 vw （viewport width）单位进行设置。1vw = 1% 的视窗宽度。例如：

  ```html
  <h1 style="font-size:10vw">Hello World</h1>
  ```

* 媒体查询（Media Queries），查询视窗的大小进行特殊的响应式布局，例如，即当视窗小于等于 800px 时，width 为 100%，当视窗大于 800px 时，使用默认样式：

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
  * {
    box-sizing: border-box;
  }
  
  .left {
    background-color: #2196F3;
    padding: 20px;
    float: left;
    width: 20%; /* The width is 20%, by default */
  }
  
  .main {
    background-color: #f1f1f1;
    padding: 20px;
    float: left;
    width: 60%; /* The width is 60%, by default */
  }
  
  .right {
    background-color: #04AA6D;
    padding: 20px;
    float: left;
    width: 20%; /* The width is 20%, by default */
  }
  
  /* Use a media query to add a break point at 800px: */
  @media screen and (max-width: 800px) {
    .left, .main, .right {
      width: 100%; /* The width is 100%, when the viewport is 800px or smaller */
    }
  }
  </style>
  </head>
  <body>
  
  <h2>Media Queries</h2>
  <p>Resize the browser window.</p>
  
  <p>Make sure you reach the breakpoint at 800px when resizing this frame.</p>
  
  <div class="left">
    <p>Left Menu</p>
  </div>
  
  <div class="main">
    <p>Main Content</p>
  </div>
  
  <div class="right">
    <p>Right Content</p>
  </div>
  
  </body>
  </html>
  ```

  视窗小于等于 800px 样式![mediaQueriesLess800px](D:\NEW\Study\markdown\pic\前端基础\mediaQueriesLess800px.png)

  视窗大于等于 800px 样式![mediaQueriesLarger800px](D:\NEW\Study\markdown\pic\前端基础\mediaQueriesLarger800px.png)

## HTML 计算机代码元素（HTML Computer Code Elements）

* 包含以下五种：

  （1）<kbd> （Keyboard Input）定义键盘的输入，显示字体默认为 monospace 

  （2）<samp> （Sample Output）定义简单的输出，显示字体默认为 monospace 

  （3）<code> 定义一串代码，如需格式化可以使用 <pre> 标签，显示字体默认为 monospace 

  （4）<var> （variable）定义变量及数学符号，显示为斜体

## HTML 语义元素（Semantic Elements）

````=>意义不大，待总结````



##  Q&A

* 不加上结束标签会出现什么问题？

* href 和 src 区别？

* 绝对路径和相对路径详解

* <html lang="en-US"> 具体作用？

* 请将标题元素只用于显示标题中，而不要使用标题元素进行加粗，为什么？

* b和strong 标签区别

  （1）两者都是加粗效果，但 b 标签是样式标签，而 strong 是语义化标签，强调文本重要

  （2）搜索引擎更加侧重于 strong 标签

  （3）最容易理解的场景就是：盲人朋友使用屏幕阅读设备阅读网络资源时，strong标签包裹的内容会被重读，而b标签包裹的内容不会被重读

* i 和 em 区别

  （1）i 是无意义的斜体，没有强调语义

  （2）em 表示强调，具有语义，搜索引擎中更加重视，语音阅读器在阅读它的时候也会增强语气

* **研究一下 GB, HEX, HSL, RGBA, or HSLA 原理** = 》 在colors中

* border、padding、margin 存在的意义？

* target 的框架属性？

* **Note:** Always specify the width and height of an image. If width and height are not specified, the web page might flicker while the image loads.But why the web will flicker?

* 实际上，图片并没有嵌入网页中，img 标签是预留了一个空间给图片，图片是以链接的方式载入的 深入理解这句话

* **研究 Images 拓展 =》 在 image 中**

* **研究 Tables 拓展 =》在Tables 中**

* 如果内联元素包含块级元素，会出现什么问题？

* 深入研究 id 和 class 复用的区别

  ![idQuestion](D:\NEW\Study\markdown\pic\前端基础\idQuestion.png)

* 研究神奇的 screen readers 

* input 标签和 button 标签区别
* 如何禁用浏览器 JavaScript，实现一次 noScript

* **Disadvantages:** Floating elements are tied to the document flow, which may harm the flexibility. Learn more about float in our [CSS Float and Clear](https://www.w3schools.com/css/css_float.asp) chapter.But why?

* 对各种单位，px、vw 的直观估计感知提升
* 研究 w3c.css 和 bootstrap.css

* 响应式布局的例题，学完 CSS 回来做
* HTML Computer Code 的几个元素的区别？以及存在意义？
* 语义化标签的意义及和 div 的区别，待总结部分
