#### 异步解码图像

效果：加快显示其他内容

   ``` html
   <img decoding="async" src="/images/logo.png" />
   ```



#### 空元素在后面关闭

   ```html
   <br/>
   ```



#### 区块

   * 块级元素用 `<div>` ，块元素是一个元素，占用了全部宽度，在前后都是换行符。
   * 行级元素用 `<span>` ，内联元素只需要必要的宽度，不强制换行。



#### 空格

   * HTML 代码中的所有连续的空行或换行会被显示为一个空格



#### 字体

   * 加粗用 `<strong>`
   * 斜体用 ` <em>`

   

#### a 标签属性

   * target = "_blank"：新建标签打开
   * target = "_self"：当前标签打开



#### GET和POST的区别

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









