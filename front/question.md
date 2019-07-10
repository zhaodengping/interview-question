

### HTML
- Q：HTML全拼(2019-06-28)
 
  A：Hyper Text Markup Language，超文本标记语言

- Q：HTML和XML(ExtentsibleMarkup Language)区别(2019-06-28)

  A：
  
  比较内容|HTML|XML
  :-:|:-:|:-:
  设计目标|显示数据，如何更好地显示数据，焦点是数据外观|描述数据，什么是数据，如何存放数据，焦点是数据的内容
  语法|不要求标记的嵌套、配对等；不区分大小写;引号是可用可不用的；可以拥有不带值的属性名；过滤掉空格；|严格要求嵌套、配对，并遵循DTD的树形结构；区分大小写；属性值必须分装在引号中；所有的属性都必须带有相应的值；空白部分不会被解析器自动删除；xml比html 语法要求更严格
  数据和显示的关系|内容描述与显示方式整合为一体|内容描述与显示方式分离
  标签|预定义|免费、自定义、可扩展
  可读性及可维护性|难于阅读、维护|结构清晰、便于阅读、维护
  结构描述|不支持深层的结构描述|文件结构嵌套可以复杂到任何程度
  与数据库的关系|没有直接联系|与关系型和层状数据库均可对应和转换
  超链接|单文件、书签链接|可以定义双向链接、多目标链接、扩展链接

- Q： 你是如何理解 HTML 语义化的？ 

  A:让HTML内容结构化， 便于开发者去阅读和编写。 常见的标签有 `table,ul,span,div` 

- Q： meta viewport 是做什么用的？ 

  A:viewport是供移动设备使用的

- Q： HTML5标签

  A： `header,main,aside,section,footer` 等

- Q： H5是什么？ 

  A： 超文本标记语言

- Q：href和src区别

  A：href是表示超文本引用，用来建立当前元素和文档之前的链接，浏览器会识别改文档为css文档，会进行下载，不会对当前文档停止渲染，
  src是指向外部资源，将指定的内容嵌入到当前位置，会停止当前文档渲染，等待这个资源加载完毕

- 怎样添加、移除、移动、复制、创建和查找节点？
  A：如下
  - 创建新节点：
  ```
  createElement()//创建具体元素
  createTextNode()//创建文本节点
  ```

  - 添加、移除、替换、插入：
  ```
  appendChild();//添加 
  removeChild();//移除
  replaceChild();//替换
  insertBefore();//插入
  ```

  - 查找
  ```
  getElementTagName();//标签
  getElementById();//id
  getElementByName();//name属性值
  ```

- Q：浏览器如何渲染页面？

  A：1、解析HTML文件，创建DOM树；2、解析CSS；3、将CSS和DOM树结合；4、布局和绘制

- Q：HTML怎么在手机端访问相册、摄像机、录音？(2019-06-28)

  A：
  ```
  <input type="file" accept="image/*" capture="camera"> //相册 
  <input type="file" accept="video/*" capture="camcorder">  //摄像机
  <input type="file" accept="audio/*" capture="microphone"> //录音
  ``` 

### CSS

- Q： 两种盒模型

  A： 分别为： 1、 W3C标准盒模型， `width=content` ; 2、 IE盒子模型： `width=content+padding+border` 。 

```
box - sizing: content - box; //W3C盒子模型
box - sizing: border - box; //IE盒子模型
```
- CSS3的属性

  A：transform,canvas,border-radius,box-shadow,background里的linear-gradient(渐变色),animation等

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

- Q：display:none和visibility:hidden区别
  
  A：display:none是直接不渲染，visibility是渲染了，只是看不见

- Q：CSS中link 和@import的区别是？

  A：link是HTML里面的标签，@import是css提供的

- Q：animation和transition区别

  A：
  - animation属性需要结合@keyFrames去使用，`@keyFrames{from{};to{}}`,而且可以设置每一帧的样式和时间

  - transition属性一般结合`:hover`去实现，只能设置头尾

### js

- Q： 基本数据类型

  A：基本数据类型： string, number, undefined, null, boolean, Symbol；引用类型：Object,Function,Array

- Q： 事件委托

  A:子事件委托给父元素去监听， 也就是事件冒泡。 可以大量节省内存占用，减少事件注册

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

      解决跨域： 1. CORS: 在后台增加响应头； 2. jsonp: 在前端得script中引入js文件， 当这个文件成功载入， callback会执行我们url中指
      定的函数， 并把json作为参数传入

    ```
      < script type = "text/javascript" >
          function dosomething(jsondata) {
              //处理获得的json数据
          } 
      </script>  
      <script src = "http://example.com/data.php?callback=dosomething" > < /script>
    ```

- Q： 实现深拷贝

  A： 1. 递归； 2. JSON.stringify(JSON.parse(a)); 

- Q： class类和原型prototype继承

 
  A： 如下
  class继承
  

```
  class Person {}
  class Child extends Person {}
  let child = new Child()
```

  prototype继承
  

```
  function parent() {};
  parent.prototype.getValue = function() {
      console.log("hahaha")
  }
  let child = new parent();
  child.getValue(); //"hahaha"
```

- Q：箭头函数和普通函数区别

  A：箭头函数this指向定义时所在的位置，普通函数指向使用时的对象

- Q： 如何实现数组去重

 
  A： 1、 `Array.from(new Set([1,2,3]))` 

- Q：数组的增删改查

  A：如下
  
  - 增：push/contact/unshift/splice

  - 删：pop/shift/splice/slice

  - 改：splice

  - 查：indexof/find

- Q：数组常用的8种方法(2019-06-28)

  A：pop,push,shift,unshift,map,filter,find,some,splice,slice,every等

- Q：splice和slice区别(2019-06-28)

  A：slice对原数组进行截取，返回新的数组，原数组不变，`slice(start,end);//不包含end`；
     splice是在原数组上进行操作，会改变原数组,`splice(start,num,newNum);//开始位置，截取数量，插入的新数据`

- Q：定时器有哪些？有什么区别？

  A:setTimeout():过一段时间再去触发；setInterval():每过一段时间都去触发

- Q：如何理解js中的原型和原型链？

  A：每个对象都有一个原型，当我们使用某个属性时，如果这个对象本身没有，就会向上的原型prototype中去查找，原型prototype本身也是有原型
  的，就会一层一层往上，形成原型链

- Q：js函数的特点(2019-06-28)

  A：js函数有以下几种形式：
     - 正常定义函数，`function a(){};//this指向window`

     - 有把函数赋值给变量，`let a=function(){};//this指向window`

     - 匿名函数,
     ```
     let obj={
       name:"zdp",
       eat:function(){
         console.log(this);//this指向是谁调用，就指向谁
       }
     }
     ```
     
     - 箭头函数,`setTimeout(()=>{console.log(this)});//箭头函数其实没有this指向，是父级的环境`
     
     - 构造函数
     ```
     function eat(){
       console.log(this)
     }
     let obj=new eat();//this指向new出来的对象
     ```
- Q:垃圾回收机制

  A：
     



### TypeScript

- Q： TypeScript对于JavaScript的优势

 
  A： 减少人为的bug， 对数据类型要求较高， 真正的面向对象， 有接口， 类， 等概念

- Q： 基本数据类型 12种

 
  A： string, Number, Array, undefined, null, boolean, object, enum, Tuple, void, any, never

### ES6

- Q： 新增语法

  A:如下
  - var:没有块级概念， 但是不能跨函数使用， 且有变量名提升； let： 只能在块级作用域中访问； const： 用来定义常量， 且必须初始化和不能修改
  - promise异步， 防止回调地狱。 
  - async和await, 让异步便同步
  - 数组和对象的扩展, [参考](https://github.com/zhaodengping/basic-web/blob/master/docs/front/es6.md)

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

- Q： cookie, session, localstorage, sessionStorage区别

  A:区别如下： 

    1. cookie： 是存放在浏览器中， 不安全， 存储容量不是很大， 同源浏览器窗口共享
    2. session： 是存放在服务端， 存储容量也不是很大
    3. localStorage： 存放在浏览器中， 存储容量大， 浏览器关闭， 缓存还存在， 同源浏览器窗口共享
    4. sessionStorage： 存放在浏览器， 但是浏览器关闭， 缓存也消失了， 同源浏览器窗口不共享

- Q：一次完整的HTTP请求

  A：1、域名解析，获取相应的IP地址；2、发起TCP连接，进行TCP的三次握手；3、发起HTTP请求；4、服务端相应HTTP请求，返回相应的数据；5、浏览器解析HTML,并请求HTML中的资源；
  6、浏览器对页面进行渲染

- Q：跨域全拼(2019-06-28)

  A：CORS:Cross-origin resource sharing(跨资源共享)

### VUE

- Q： vue的响应原理

  A： 观察者模式和订阅-发布者模式。 Vue实例被创建时，会遍历data属性，并通过Object.defineProperty将 这些属性转化为getter/setter，并进行追踪依赖。每当data属性值被修改时，通知watcher 实例，使得跟他相关的组件进行更新

- Q：Object.defineProperty()如何创建对象

  A：
  ```
  Object.defineProperty(obj, prop, descriptor);//obj为目标对象，prop是定义或修改属性的名字，descriptor是目标对象属性的特性
  ```
  ```
  let obj={
    test:"hello"
  }
  Object.defineProperty(obj,"test",{
    value:1
  })
  ```

- Q：vue的标签

  A：router-view,router-link,transition,slot,keep-alive

- Q：watch,computed区别

  A：watch:监听，computed:data可以不用去定义这个变量，有缓存，只要他相关的依赖没有发生变化，就不会重新去计算

- Q：组件通信

  A：父传子:prop,子传父:$emit，平级：bus

- Q：Vue.$set是用于什么

  A：如果在实例创建之后添加新的属性到实例上，它不会触发视图更新，这时用Vue.$set，会刷新到视图上(这也是Vue的缺点之一)

- Q：$route和$router区别

  A：$router是实例，包括跳转；$route是路由信息对象，包括path，param等信息

- Q：浏览器内核的理解

  A：浏览器内核包括js引擎和渲染引擎。渲染引擎负责渲染网页内容，js引擎实现动态效果 

- Q：如何实现工程化？(2019-06-28)

  A：模块化和组件化

- Q：vue最小能实现什么功能(2019-06-28)

  A：模板template

- Q：vuex

  A：

### 性能优化

- 合并 CSS 和 JS 文件，通过前端打包工具去压缩和打包

- 懒加载，控制页面内容一开始无需加载，等到用户真正需要的时候再进行加载内容

- 浏览器缓存

- 页面使用class去操作样式，因为style会让浏览器重新计算DOM值，重新渲染DOM树，使得浏览器加载变慢

### 其他方面

- Q：最近读什么有关技术的书？

- Q：有关注哪个大佬？

- Q：写代码时会遇到什么困难？如何解决？
