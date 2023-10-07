1. 异步解码图像，加快显示其他内容

   ``` html
   <img decoding="async" src="/images/logo.png" />
   ```

2. 空元素一样是在后面关闭的

   ```html
    <br/>
   ```

3. 样式

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

4. 区块

   * 块级元素用 `<div>`
   * 行级元素用 `<span>`

5. HTML 代码中的所有连续的空行或换行会被显示为一个空格

6. 字体

   * 加粗用 `<strong>`
   * 斜体用 ` <em>`

7. a 标签属性

   * target = "_blank"：新建标签打开
   * target = "_self"：当前标签打开

