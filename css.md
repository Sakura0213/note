#### 选择器

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



#### 组合选择器

- 后代选择器(以空格 ` ` 分隔)
- 子元素选择器(以大于 `>` 号分隔）
- 相邻兄弟选择器（以加号 `+` 分隔）
- 普通兄弟选择器（以波浪号 `~` 分隔）

``` css
<!--所有div标签的所有后代p标签-->
div p
{
  background-color:yellow;
}

<!--所有div标签的所有后一代p标签-->
div>p
{
  background-color:yellow;
}

<!--所有div标签的相邻同代p标签-->
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



#### 分组选择器

使用逗号分隔

``` css
h1,h2,p
{
    color:green;
}
```



#### 属性选择器

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



#### 样式

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

样式优先级：

内联样式 > 内部样式 > 外部样式 > 浏览器默认样式



#### 文本对齐

``` css
/* 水平方向对齐 */
text-align:right;

/* 垂直方向对齐 */
vertical-align:bottom;
```



#### 文本转换

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



#### 文本缩进

文本缩进属性是用来指定文本的第一行的缩进。

``` css
p {
    text-indent:50px;
}
```



#### 伪类列表

https://www.runoob.com/css/css-pseudo-classes.html



#### 盒子模型

 ![image-20231007153653076](http://zengxinyou.test.upcdn.net/ocq/image-20231007153653076.png)

- **Margin(外边距)**：清除边框外的区域（透明）
- **Border(边框)**：围绕在内边距和内容外的边框（可上色）
- **Padding(内边距)**：清除内容周围的区域（透明）
- **Content(内容)**：盒子的内容，显示文本和图像



#### 边框

``` css
/*实线边框*/
border-style:solid;
```



#### 可见性

* visibility:hidden 可以隐藏某个元素，但隐藏的元素仍需占用与未隐藏之前一样的空间。也就是说，该元素虽然被隐藏了，但仍然会影响布局。
* display:none 可以隐藏某个元素，且隐藏的元素不会占用任何空间。也就是说，该元素不但被隐藏了，而且该元素原本占用的空间也会从页面布局中消失。



#### 切换行级和块级

``` css
div {
    display:inline;
}

span {
    display:block;
}
```



#### 定位

https://www.runoob.com/css/css-positioning.html



#### overflow

overflow 属性用于控制内容溢出元素框时显示的方式。

 ![image-20231007163442312](http://zengxinyou.test.upcdn.net/ocq/image-20231007163442312.png) ![image-20231007163536470](http://zengxinyou.test.upcdn.net/ocq/image-20231007163536470.png)



#### 对齐

https://www.runoob.com/css/css-align.html

元素居中对齐，margin 和 width 需要同时使用

``` css
.center {
    margin: auto;
    width: 50%;
}
```



#### !important

!important 规则用于增加样式的权重。**!important** 与优先级无关，但它与最终的结果直接相关，使用一个 !important 规则时，此声明将覆盖任何其他声明。

- **一定**要优先考虑使用样式规则的优先级来解决问题而不是 `!important`
- **只有**在需要覆盖全站或外部 CSS 的特定页面中使用 `!important`
- **永远不要**在你的插件中使用 `!important`
- **永远不要**在全站范围的 CSS 代码中使用 `!important`



#### 简写

``` css
border:2px solid #a1a1a1;
```



