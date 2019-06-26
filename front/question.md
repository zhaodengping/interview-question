

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

  A： 如下
  
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

- Q：基本数据类型

  A：string,number,undefined,null,boolean,Symbol

- Q： 事件委托

  A:子事件委托给父元素去监听， 也就是事件冒泡。 

- Q: 函数防抖和节流

  
  A:函数防抖： 让某个函数在某段时间内不被调用后执行； 节流： 是在某段时间内， 最多调用一次。 [例子参考](https://www.jianshu.com/p/b7b698db8352)

- Q： ajax的参数

  A： 如下
  

```
  $.ajax({
      url: url,
      type: "",
      data: "",
      dataType: "",
      success: function() {},
  })
```

- Q： 闭包和立即执行函数的理解

  A： 闭包： 是有权访问其他函数的变量； 立即执行函数： 声明一个函数并能立即执行

- Q： 什么是跨域？ 如何解决跨域

  A： 跨域： 浏览器同源策略， 协议、 域名、 端口号不一致导致； 

      解决跨域： 1. CORS: 在后台增加响应头； 2. jsonp: 在前端得script中引入js文件，当这个文件成功载入，callback会执行我们url中指定的函数，并把json作为参数传入

    ```
      <script type = "text/javascript" >
          function dosomething(jsondata) {
              //处理获得的json数据
          } 
      </script> 
      <script src = "http://example.com/data.php?callback=dosomething" > < /script>
    ```
- Q：实现深拷贝

  A：1.递归；2.JSON.stringify(JSON.parse(a));

- Q：class类和原型prototype继承
 
  A：如下
  class继承
  ```
  class Person{}
  class Child extends Person{}
  let child=new Child()
  ```
  prototype继承
  ```
  function parent(){};
  parent.prototype.getValue=function(){
      console.log("hahaha")
  }
  let child=new parent();
  child.getValue();//"hahaha"
  ```

- Q：如何实现数组去重
 
  A：1、`Array.from(new Set([1,2,3]))`

### TypeScript

- Q：TypeScript对于JavaScript的优势
 
  A：减少人为的bug，对数据类型要求较高，真正的面向对象，有接口，类，等概念

- Q：基本数据类型 12种
 
  A：string,Number,Array,undefined,null,boolean,object,enum,Tuple,void,any,never

### ES6

- Q： 新增语法

  A:如下
  1. var:没有块级概念， 但是不能跨函数使用， 且有变量名提升； let： 只能在块级作用域中访问； const： 用来定义常量， 且必须初始化和不能修改
  2. promise异步， 防止回调地狱。 
  3. async和await, 让异步便同步
  4. 数组和对象的扩展, [参考](https://github.com/zhaodengping/basic-web/blob/master/docs/front/es6.md)

- Q： Promise、 Promise.all、 Promise.race区别

  
  A： 如下
  - promise： 单个异步

  - Promise.all： 将多个异步放一起， 结果一一显示

  - Promise.race： 哪个异步出的结果快， 就返回哪一个

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

