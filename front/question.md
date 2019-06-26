

### HTML

- Q： 你是如何理解 HTML 语义化的？ 

  A:让HTML内容结构化， 便于开发者去阅读和编写。 常见的标签有 `table,ul,span,div` 

- Q： meta viewport 是做什么用的？ 

  A:viewport是供移动设备使用的

- Q： HTML5标签

  A： `header,main,aside,section,footer` 等

- Q： H5是什么？ 

  A： 超文本标记语言

### CSS

- Q： 两种盒模型

  A： 分别为： 1、 W3C标准盒模型， `width=content` ; 2、 IE盒子模型： `width=content+padding+border` 。 

```
box - sizing: content - box; //W3C盒子模型
box - sizing: border - box; //IE盒子模型
```

- Q： 垂直居中

  A：如下
  
  1、 单行文字

```
.father1 {
    width: 300 px;
    height: 300 px;
    border: 1 px solid# f2f2f2;
}
.child1 {
    text - align: center;
    line - height: 300 px;
}
```

  2、 多行文字

```
.father2 {
    display: table;
    width: 200 px;
    height: 300 px;
    border: 1 px solid# f2f2f2;
}
.child2 {
    display: table - cell;
    vertical - align: middle;
}
```

  3、 transform

```
.father3 {
    position: relative;
    width: 200 px;
    height: 300 px;
    border: 1 px solid# f2f2f2;
}

.child3 {
    position: absolute;
    left: 50 % ;
    top: 50 % ;
    transform: translate(-50 % , -50 % )
}
```

  4、 flex

```
.father4 {
    width: 200 px;
    height: 300 px;
    border: 1 px solid# f2f2f2;
    display: flex;
    justify - content: center;
    align - items: center;
}
```

- Q： flex布局常用属性

  A:flex弹性布局， 常用属性有 `justify-content,align-items,flex-wrap,flex-direction` 等

- Q: BFC是什么

  A： 是一块独立渲染的区域， 满足几个条件 `position:fixed/absolute;display:inline-block;overflow:hidden/scroll` 等

- Q： CSS选择器优先级

  A:!important > style样式 > id选择器 > 类选择器 > 标签 

- Q： 清除浮动

  A： `clear:both;overflow:hidden/auto;` 

### js

- Q： 事件委托

  A:子事件委托给父元素去监听， 也就是事件冒泡。 

- Q:

### ES6

- Q： 新增语法

  A:

### HTTP

- Q： HTTP的状态码有哪些？ 分别是什么意思？ 

  A： 2**： 请求成功； 3**： 重定向； 4**:客户端请求错误； 5**:服务器错误

- Q： GET和POST有什么区别

  A:GET和POST本质上没什么区别， 但是

1. GET参数是在url中， 而POST是通过body去传参数； 
2. GET因为参数都在url中， 所以比POST安全性低点； 
3. GET会被浏览器自动计入缓存， 而POST不会; 

- Q： cookie， session, localstorage, sessionStorage区别

  A:区别如下： 

1. cookie： 是存放在浏览器中， 不安全， 存储容量不是很大， 同源浏览器窗口共享
2. session： 是存放在服务端， 存储容量也不是很大
3. localStorage： 存放在浏览器中， 存储容量大， 浏览器关闭， 缓存还存在， 同源浏览器窗口共享
4. sessionStorage： 存放在浏览器， 但是浏览器关闭， 缓存也消失了， 同源浏览器窗口不共享

