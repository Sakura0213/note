## html

### 异步解码图像

效果：加快显示其他内容

   ``` html
   <img decoding="async" src="/images/logo.png" />
   ```



### 自闭合标签

   ```html
   <br/> <input/> <img/> <link/> <hr/>
   ```

在后面关闭



### 区块

   * 块级元素用 `<div>` ，块元素是一个元素，占用了全部宽度，在前后都是换行符。
   * 行级元素用 `<span>` ，内联元素只需要必要的宽度，不强制换行。

常见问题：

* p元素不能包含任何块级元素(包括自身)
* a元素可以包含任何其他元素(除了自身) 
* document是文档(整个DOM树)的根节点    



#### 常见块状、内联元素

块状：`<div>、<p>、<h1>...<h6>、<ol>、<ul>、<dl>、<table>、<address>、<blockquote> 、<form> ` 

内联：`<a>、<span>、<br>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>  `

内联块状： `<img>、<input>  `（为行内元素，但是有行内块   ）



#### 块状、内联元素的宽高

内联元素是不可以控制宽和高、margin等；并且在同一行显示，不换行。  

   块级元素时可以控制宽和高、margin等，并且会换行。  

1. inline ： 使用此属性后，元素会被显示为内联元素，元素则不会换行   

   inline是行内元素，同行可以显示，像span、font、em、b这些默认都是行内元素，不会换行，无法设置宽度、高度、margin、border  

2. block ： 使用此属性后，元素会被现实为块级元素，元素会进行换行。   

   block，块元素，div、p、ul、li等这些默认都是块元素，会换行，除非设置float   

3. inline-block ： 是使元素以块级元素的形式呈现在行内。意思就是说，让这个元素显示在同一行不换行，但是又可以控制高度和宽度，这相当于内敛元素的增强。(IE6不支持)   

   inline-block，可以同行显示的block，想input、img这些默认就是inline-block，出了可以同行显示，其他基本block一样  



### 空格

   * HTML 代码中的所有连续的空行或换行会被显示为一个空格



### 字体

   * 加粗用 `<strong>`
   * 斜体用 ` <em>`

   

### a 标签属性

   * target = "_blank"：新建标签打开
   * target = "_self"：当前标签打开



### 超链接 URL

超链接的 URL可能的值：

- 绝对 URL - 指向另一个站点（比如 href="http://www.example.com/index.htm"）
- 相对 URL - 指向站点内的某个文件（href="index.htm"）
- 锚 URL - 指向页面中的锚（href="#top"）

`<a href=”mailto:love@baidu.com”>love@baidu.com</a>`



### GET和POST的区别

   * 主要
     * GET请求会被浏览器主动缓存，POST不会。
     * GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留。
     * 对参数的数据类型，GET只接受ASCII字符， 而POST没有限制。
     * GET请求在URL中传送的参数是有长度限制的，而POST没有。
     * GET参数通过URL传递，所以不能用来传递敏感信息，POST放在Request body中。

   * 其他
     * GET在浏览器回退时是无害的，而POST会再次提交请求。
     * GET产生的URL地址可以被Bookmark,而POST不可以。
     * GET请求只能进行url编码，而POST支持多种编码方式。



### 语义化

语义化是html不断发展的结果，就是看到标签的名字就知道这个标签是干什么的意思，比如hearder就是标题，footer就是结尾，video就是视频，反过来就是反语义化了。    







### iframe

**局限：** 

   1、创建比一般的 DOM 元素慢了 1-2 个数量级  

   iframe 的创建比其它包括 scripts 和 css 的 DOM 元素的创建慢了 1-2 个数量级，使用 iframe 的页面一般不会包含太多 iframe，所以创建 DOM 节点所花费的时间不会占很大的比重。但带来一些其它的问题：onload 事件以及连接池（connection pool）  

   2、阻塞页面加载  

   及时触发 window 的 onload 事件是非常重要的。onload 事件触发使浏览器的 “忙” 指示器停止，告诉用户当前网页已经加载完毕。当 onload 事件加载延迟后，它给用户的感觉就是这个网页非常慢。  

   window 的 onload 事件需要在所有 iframe 加载完毕后（包含里面的元素）才会触发。在 Safari 和 Chrome 里，通过 JavaScript 动态设置 iframe 的 SRC 可以避免这种阻塞情况  

   3、唯一的连接池  

   浏览器只能开少量的连接到 web 服务器。比较老的浏览器，包含 Internet Explorer 6 & 7 和 Firefox 2，只能对一个域名（hostname）同时打开两个连接。这个数量的限制在新版本的浏览器中有所提高。Safari 3+ 和 Opera 9+ 可同时对一个域名打开 4 个连接，Chrome 1+, IE 8 以及 Firefox 3 可以同时打开 6 个  

   绝大部分浏览器，主页面和其中的 iframe 是共享这些连接的。这意味着 iframe 在加载资源时可能用光了所有的可用连接，从而阻塞了主页面资源的加载。如果 iframe 中的内容比主页面的内容更重要，这当然是很好的。但通常情况下，iframe 里的内容是没有主页面的内容重要的。这时 iframe 中用光了可用的连接就是不值得的了。一种解决办法是，在主页面上重要的元素加载完毕后，再动态设置 iframe 的 SRC。  

   4、不利于 SEO  

   搜索引擎的检索程序无法解读 iframe。另外，iframe 本身不是动态语言，样式和脚本都需要额外导入。综上，iframe 应谨慎使用。  



### readonly

readonly 属性规定输入字段为只读,只读字段是不能修改的。不过，用户仍然可以使用 tab 键切换到该字段，还可以选中或拷贝其文本。   

disabled才不可以选中。     



### 强调标签

 ![image-20231008160433660](http://zengxinyou.test.upcdn.net/ocq/image-20231008160433660.png)



### 图形验证码

服务器端生成验证码后一方面通过图片将验证码返回给客户端,同时在服务器端保存文本的验证码,由服务器端验证输入内容是否正确。



### HTML 音频/视频 方法 

| 方法                                                         | 描述                                      |
| :----------------------------------------------------------- | :---------------------------------------- |
| [addTextTrack()](https://www.runoob.com/tags/av-met-addtexttrack.html) | 向音频/视频添加新的文本轨道。             |
| [canPlayType()](https://www.runoob.com/tags/av-met-canplaytype.html) | 检测浏览器是否能播放指定的音频/视频类型。 |
| [load()](https://www.runoob.com/tags/av-met-load.html)       | 重新加载音频/视频元素。                   |
| [play()](https://www.runoob.com/tags/av-met-play.html)       | 开始播放音频/视频。                       |
| [pause()](https://www.runoob.com/tags/av-met-pause.html)     | 暂停当前播放的音频/视频。                 |

```
方法：load() play() pause()
事件：play() playing() pause() seeked() seeking() abort()当音频/视频的加载已放弃时触发
```



### 单选框和复选框

radio:单选框

checkbox:复选框



### 显示缩写标签

```html
The <abbr title="People's Republic of China">PRC</abbr> was founded in 1949.
```



### 表单input type

 ![image-20231008165524596](http://zengxinyou.test.upcdn.net/ocq/image-20231008165524596.png)

date和datetime-local都支持修改时间

 ![ ](http://zengxinyou.test.upcdn.net/ocq/50FA601285A94F690B61787B2B8B3B31)

range

 <img src="http://zengxinyou.test.upcdn.net/ocq/350480372_1605454018673_3A5EB5EE7BDB6EDAD96424A428C71762" alt="img" style="zoom: 50%;" />



### select

``` html
<form name="a">
    <select name="a" size="1" id=”obj”>
        <option value="a">1</option>
        <option value="b">2</option>
        <option value="c">3</option>
    </select>
</form> 
```

``` javascript
window.onload = function(){ 

//首先获得下拉框的节点对象；  

var obj = document.getElementById("obj"); 

//1.如何获得当前选中的值？：  

var value = obj.value; 

//2.如何获得该下拉框所有的option的节点对象   

var options = obj.options; 

//注意：得到的options是一个对象数组  

//3.如何获得第几个option的value值?比如我要获取第一option的value,可以这样：  

var value1 =options[0].value; 

//4.如何获得第几个option的文本内容?比如我要获取第一option的文本,可以这样：  

var text1 = options[0].text; 

//5.如何获得当前选中的option的索引？  

var index = obj.selectedIndex; 

//6.如何获得当前选中的option的文本内容？  

//从第2个问题，我们已经获得所有的option的对象数组options了  

//又从第5个问题，我们获取到了当前选中的option的索引值  

//所以我们只要同options[index]下标的方法得到当前选中的option了  

var selectedText =options[index].text; 

} 
```





### textarea

textarea：多行文本输入框    

 ![image-20231008181724367](http://zengxinyou.test.upcdn.net/ocq/image-20231008181724367.png)



### 屏幕的尺寸标准

 ![image-20231008181921114](http://zengxinyou.test.upcdn.net/ocq/image-20231008181921114.png)



### 列表

* 有序列表：

  ``` html
  <ol>
  	<li>Coffee</li>
  	<li>Milk</li>
  </ol>
  ```

* 无序列表：

  ``` html
  <ul>
  	<li>Coffee</li>
  	<li>Milk</li>
  </ul>
  ```

* 自定义列表

  ``` html
  <dl>
      <dt>标题</dt>
      <dd>内容</dd>
  </dl>
  ```



### canvas

* canvas是HTML5的一部分，允许脚本动态渲染位图像
* canvas拥有多种绘制路径、矩形、圆形、字符及添加图像的方法
* Internet Explorer自Internet Explorer9起已经可以支持canvas



### Window对象

![image-20231009141844854](http://zengxinyou.test.upcdn.net/ocq/image-20231009141844854.png)



### 时间组件

date  选取日、月、年 

month 选取月和年 

week  选取周和年 

time  选取时间（小时和分钟）



### 常见错误

* 在下列标签中，哪个标签表示最小的标题？h6，没有h7。
* `<ul>下不能直接放置<p>`
* 调用canvas对象的getContext方法来获取绘图环境
* meter标签类似于进度条，按百分比显示。 input的type属性可以设置为range，范围可调。
* video是作为Flash的替代技术出现
* head 标签中必不少的是标题title和编码meta






## html5

### 新增标签

 ![image-20231008141105676](http://zengxinyou.test.upcdn.net/ocq/image-20231008141105676.png)

picture
meter标签用于显示已知范围内的标量测量值。



1. 注意题目问的是类型/元素/属性 
2.  新增的表单元素：output、datalist、keygen
3. 新增的表单类型(type="xxx"):color设色器、date日期选择器、datetime(utc时间)、datetime-local(无时区)   email(包含email的输入域)、month（月份）、number（数值）、range(范围)、search（搜索）、tel(电话号码)   url、week 
4. 新增的表单属性：autocomplete（自动补全）、autofocus（自动聚焦）、required(是否必选)、height（高度）、width（宽度）    multiple（多文件上传）、max（最大值）、min、step、list、pattern（模式匹配/正则）、placeholder（默认值）、novalidate(提交表单时不校验email/tel这些需要校验的表单类型)、    form（表单元素可以在form之外，但是可以指定属于哪个form，会一起发送）、formaction（请求地址）、formmethod（form元素的请求方法,get/post这些）、formenctype、formnovalidate



manifest 属性规定文档的缓存 manifest 的位置，manifest 文件是一个简单的文本文件，列举出了浏览器用于离线访问而缓存的资源。



### 储存

 HTML5中增加了两种全新的数据存储方式：WebStorage和WebSQLDatabase。 

* WebStorage：临时或永久保存客户端的少量数据。 分为两种：
  * sessionStorage(浏览器关闭则消失)
  * loaclStorage(在自己的内存中保留，浏览器关闭还存在)。 

​    保存数据：调用setItem()方法，格式：sessionStorage.setItem(key,value)

​    读取数据：调用对象中的getItem()方法，格式：localStorage.getItem(key)

* WebSQLDatabase：是客户端本地化的一套数据库系统，可以将大量的数据保存在客户端，无须与服务器端进行交互，极大地减轻了服务器端的压力。







## css

### 选择器

``` css
/* 选择所有的p标签 */
p {
    text-align:center;
}

/* 选择所有class="center"的p标签 */
p.center {
    text-align:center;
}
```



### 组合选择器

- 后代选择器(以空格 ` ` 分隔)
- 子元素选择器(以大于 `>` 号分隔）
- 相邻兄弟选择器（以加号 `+` 分隔）
- 普通兄弟选择器（以波浪号 `~` 分隔）

``` css
<!--所有div标签的所有后代p标签，不管多少级-->
div p
{
  background-color:yellow;
}

<!--所有div标签的所有后一代p标签-->
div>p
{
  background-color:yellow;
}

<!--所有div标签的相邻同代的后一个p标签-->
div+p
{
  background-color:yellow;
}

<!--所有div标签的所有同代p标签-->
div~p
{
  background-color:yellow;
}
```



### 分组选择器

使用逗号分隔

``` css
h1,h2,p
{
    color:green;
}
```



### 属性选择器

属性选择器样式无需使用class或id的形式

``` css
[title]
{
	color:blue;
}

<h1 title="Hello world">Hello world</h1>
```

``` css
input[type="text"]
{
	width:150px;
	display:block;
	margin-bottom:10px;
	background-color:yellow;
}

<form name="input" action="" method="get">
	Firstname:<input type="text" name="fname" value="Peter" size="20">
</form>
```



### 样式位置

   ```html
<!--内联样式-->
<p style="background-color:green;">这是一个段落</p>

<!--内部样式表-->
<!--在<head>区域使用<style>元素来包含CSS-->
<head>
    <style type="text/css">
      body {
        background-color: yellow;
      }
      p {
        color: blue;
      }
    </style>
</head>

<!--外部样式表-->
<head>
	<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
   ```



### 加载和解析

``` html
<!--外部样式表-->
<head>
	<link rel="stylesheet" type="text/css" href="main1.css">
    <link rel="stylesheet" type="text/css" href="main2.css">
</head>
```

* main1.css 和 main2.css 同时开始加载，先加载完成的优先解析
* 如果 main1.css 和 main2.css 中有相同的选择器规则，那么 main2.css 中的规则将覆盖 main1.css 的规则
* 加载是并行的，解析是顺序的



### css加载阻塞

* css加载不会阻塞DOM树的解析  

* css加载会阻塞DOM树的渲染  

* css加载会阻塞后面js语句的执行  





### 样式优先级

内联样式 > 内部样式 > 外部样式 > 浏览器默认样式

1、!important，加在样式属性值后，优先级最高，权重值：10000
 2、内联样式，如：`<div style=""></div>`，权重值：1000
 3、ID选择器，如：#app，权重值：100
 4、类选择器，伪类选择器和属性选择器，如： .content、:hover、a[href]，权重值：10
 5、标签选择器和伪元素选择器，如：div、p、:first-line、:before，权重值：1
 6、通用选择器（*）、子选择器（>）、相邻选择器（+）、同胞选择器（~），权重值：0

例子：

 ![img](http://zengxinyou.test.upcdn.net/ocq/5918115_1479277228464_E32BB148C7AF99C0CB9976B46A436D1E)

  标签的权重是1，类的权重是10 ，id的权重是100 

  ul#related span 的权重为 1+100+1=102 

  \#favorite .highlight 的权重为 100+10=110 

  highlight 的权重为 10



### 文本对齐

``` css
/* 水平方向对齐 */
text-align:right;

/* 垂直方向对齐 */
vertical-align:bottom;
```



### 文本转换

``` css
/* 大写 */
p.uppercase {
	text-transform:uppercase;
} 

/* 小写 */
p.lowercase {
    text-transform:lowercase;
} 

/* 每个单词的首字母大写 */
p.capitalize {
    text-transform:capitalize;
}
```



### 文本缩进

文本缩进属性是用来指定文本的第一行的缩进。

``` css
p {
    text-indent:50px;
}
```



### 伪类列表

https://www.runoob.com/css/css-pseudo-classes.html

选择器匹配作为任何元素的第一个子元素的 <p> 元素：p:first-child {    color:blue; }



### 盒子模型

 ![image-20231007153653076](http://zengxinyou.test.upcdn.net/ocq/image-20231007153653076.png)

- **Margin(外边距)**：清除边框外的区域（透明）
- **Border(边框)**：围绕在内边距和内容外的边框（可上色）
- **Padding(内边距)**：清除内容周围的区域（透明）
- **Content(内容)**：盒子的内容，显示文本和图像



### 边框

``` css
/*实线边框*/
border-style:solid;
```

当定义border:none时，表示无边框样式，浏览器并不会对边框进行渲染，也就没有实际的宽度。



### 可见性

* visibility:hidden 可以隐藏某个元素，但隐藏的元素仍需占用与未隐藏之前一样的空间。也就是说，该元素虽然被隐藏了，但仍然会影响布局。
* display:none 可以隐藏某个元素，且隐藏的元素不会占用任何空间。也就是说，该元素不但被隐藏了，而且该元素原本占用的空间也会从页面布局中消失。

 <img src="http://zengxinyou.test.upcdn.net/ocq/CEDE25B56863D77EB345873511CB79FD" alt="img" style="zoom:67%;" />



### 切换行级和块级

``` css
div {
    display:inline;
}

span {
    display:block;
}
```



### 定位

https://www.runoob.com/css/css-positioning.html



### overflow

overflow 属性用于控制内容溢出元素框时显示的方式。

 ![image-20231007163442312](http://zengxinyou.test.upcdn.net/ocq/image-20231007163442312.png) 

 ![image-20231007163536470](http://zengxinyou.test.upcdn.net/ocq/image-20231007163536470.png)



### 对齐

https://www.runoob.com/css/css-align.html

元素居中对齐，margin 和 width 需要同时使用

``` css
.center {
    margin: auto;
    width: 50%;
}
```



### !important

!important 规则用于增加样式的权重。**!important** 与优先级无关，但它与最终的结果直接相关，使用一个 !important 规则时，此声明将覆盖任何其他声明。

- **一定**要优先考虑使用样式规则的优先级来解决问题而不是 `!important`
- **只有**在需要覆盖全站或外部 CSS 的特定页面中使用 `!important`
- **永远不要**在你的插件中使用 `!important`
- **永远不要**在全站范围的 CSS 代码中使用 `!important`



### 简写

``` css
border:2px solid #a1a1a1;
```



### BFC

https://blog.csdn.net/XNHYJSL/article/details/116053794?spm=1001.2014.3001.5501

BFC(Block formatting context)直译为"块级格式化上下文"。它是一个独立的渲染区域，只有Block-level box参与, 

  哪些情况会产生BFC: 

1. 根元素      
2. float属性不为none      
3. position为absolute或fixed      
4. display为inline-block, table-cell, table-caption, flex, inline-flex      
5. overflow不为visible     



### 高度塌陷

![image-20231008182059257](http://zengxinyou.test.upcdn.net/ocq/image-20231008182059257.png)



### opacity

opacity属性用于设置元素的透明度级别



### 长度单位

- 相对单位：em,ex,ch,rem,vw,vh,vmax,vmin         
- 绝对单位：cm,mm,q,in,pt,pc,px         



### 继承属性

当元素的一个继承属性没有指定值时，则取父元素的同属性的计算值：

不可继承：display，margin，border，padding，background，height，width，position（百度的）

可继承：跟文字相关的一般都是继承属性



### 命名

在js里面添加的属性名使用驼峰法，在css里面使用连接线。`fontSize` `font-size`



### 文档流

浮动（float）、固定定位（fixed）和绝对定位（absolute）都会使元素脱离文档流。

CSS中脱离文档流，也就是将元素从普通的布局排版中拿走，其他盒子在定位的时候，会当做脱离文档流的元素不存在而进行定位。



### 回流、重绘

https://segmentfault.com/a/1190000017329980#item-4



1.解析HTML并构建DOM树
2.构建render树
3.布局render树
4.绘制render树



![image-20231009140723492](http://zengxinyou.test.upcdn.net/ocq/image-20231009140723492.png)



### text-shadow

text-shadow 属性中的四个值 (length、length、length、color) 分别是x轴偏移，y轴偏移，r模糊半径，c阴影颜色   



## js

### script放置位置

``` javascript
<!DOCTYPE html>
<html>
  <!--放在head中-->
  <head>
    <script>
      document.write("<p>这是一个段落</p>");
    </script>
  </head>
  <!--放在body中-->
  <body>
    <script>
      document.write("<p>这是一个段落</p>");
    </script>
  </body>
</html>

<!--外部js-->
<!DOCTYPE html>
<html>
  <body>
    <script src="myScript.js"></script>
  </body>
</html>
```

外部js同样可以放置于 <head> 或者 <body>中



### js数据输出

- 使用 **document.write()** 方法将内容写到 HTML 文档中。
- 使用 **innerHTML** 写入到 HTML 元素。

``` javascript
<!DOCTYPE html>
<html>
  <body>
    
    <!-- 修改元素 -->
    <p id="demo">我的第一个段落</p>
    <script>
      document.getElementById("demo").innerHTML = "段落已修改。";
    </script>

    <!-- 直接输出到文档 -->
    <script>
      document.write(Date());
    </script>

    <!-- 点击按钮后，页面将会被重置 -->
    <p>我的第一个段落。</p>
    <button onclick="myFunction()">点我</button>
    <script>
      function myFunction() {
        document.write(Date());
      }
    </script>

  </body>
</html>
```



### DOM取值

* .value() 用在表单元素上，用来设置获取 input 或 select 的值 
* .html() 设置或返回的是源代码 
* .text() 设置或返回的是纯文本内容 
* .attr() 设置或返回被选元素的属性值 



### DOM树

DOM树一共有12种节点类型，常用的有4种：

1、Document类型（document节点）——DOM的“入口点”

2、Element节点（元素节点）——HTML标签，树构建块

3、Text类型（文本节点）——包含文本

4、Comment类型（注释节点）——有时我们可以将一些信息放入其中，它不会显示，但JS可以从DOM中读取它。



### 事件对象

* DOM中的事件对象：（符合W3C标准） 
  * preventDefault()     取消事件默认行为  
  * stopImmediatePropagation() 取消事件冒泡同时阻止当前节点上的事件处理程序被调用。  
  * stopPropagation()    取消事件冒泡对当前节点无影响。  
* IE中的事件对象：  
  * cancelBubble()      取消事件冒泡  
  * returnValue()       取消事件默认行为  





## js面试题

**我图片复制之后，怎么样才能让这个链接不是有效的？**

使用防盗链技术，你可以配置服务器以拒绝来自不被授权的来源的请求。这可以通过设置 HTTP Referer 头来实现，从而确保只有特定网站可以访问图片。



**`querySelectorAll()` 方法返回值拿到的数组可以使用 `forEach()` 来迭代吗，为什么？**

可以，拿到的数组是 `NodeList` ，由于 `NodeList` 对象实现了迭代器协议，所以可以被 `forEach` 方法处理。还可以使用 `Array.from()` 将类数组转换为数组后再进行迭代。



**类数组怎么转成数组？**

使用 `Array.from()` 方法



 **`Array.from()` 方法的原理？**

原理是遍历输入对象的元素，并将它们复制到一个新的数组中，最后返回这个新数组。



**已知js有一个insertBefore的api，那么我要怎么实现insertAfter呢？**

原方法是在旧节点之前插入一个新节点，after方法可调用这个原方法，在旧节点的下一相邻兄弟节点之前插入这个新节点。

`nextSibling`，即指向元素的下个兄弟元素，如果已经是末尾子节点则为null。

``` javascript
//语法
parentElement.insertBefore(newElement, referElement)

function insertAfter(newNode, referenceNode) {
    referenceNode.parentNode.insertBefore(newNode, referenceNode.nextSibling);
}
```





