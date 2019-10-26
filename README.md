# 前端面试笔记
> 跨域

 指的是浏览器不能执行其他网站的脚本。它是由浏览器的同源策略造成的，是浏览器对javascript施加的安全限制
 
> 行列元素和块级元素区别

行内元素
与其他行内元素并排
不能设置宽高，默认的宽度就是文字的宽度

块级元素一定的范围,可以设置宽高

>Null和Undefined的区别


1、undefined
　表示"缺少值"，就是此处应该有一个值，但是还没有定义
　典型用法是：
　　（1）变量被声明了，但没有赋值时，就等于undefined。
　　（2) 调用函数时，应该提供的参数没有提供，该参数等于undefined。
　　（3）对象没有赋值的属性，该属性的值为undefined。
　　（4）函数没有返回值时，默认返回undefined。

2、null
　表示"没有对象"，即该处不应该有值。
　典型用法是：
　　（1） 作为函数的参数，表示该函数的参数不是对象。
　　（2） 作为对象原型链的终点


> 固定宽高垂直居中

```
position: absolute;
left: 50%;
top: 50%;
width:200px;
height:100px;
margin-left:-100px;
margin-top:-50px;
```
>对前端性能优化有什么了解？

1.代码层面：规范代码，少用闭包，代码压缩
2.网络请求层面：减少网络请求次数，合理配置http缓存，使用内容分发网页cdn，减少cookies传输



> react的生命周期分为三个阶段：

Mounting 挂载
render 渲染
Updating 更新
Unmounting 卸载

> postion(定位)

`absolute`	
生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。

元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。

`fixed`
生成绝对定位的元素，相对于浏览器窗口进行定位。

元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。

`relative`	
生成相对定位的元素，相对于其正常位置进行定位。

因此，"left:20" 会向元素的 LEFT 位置添加 20 像素。

`static`	
默/认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。
inherit	规定应该从父元素继承 position 属性的值。
>闭包

 函数内定义的函数可以调用外部函数的变量
 ###### 好处:
 1.希望一个变量长期存储在内存中。
 2.避免全局变量的污染。
 3.私有成员的存在。
  ###### 缺点:
 1.常驻内存，增加内存使用量。
 2.使用不当会很容易造成内存泄露。
>JavaScript里arguments究竟是什么？

arguments虽然有一些数组的性质，但其并非真正的数组，只是一个类数组对象。

>事件委托

事件委托就是利用事件冒泡，指定一个事件处理程序，就可以管理某一类型的所有事件,事件冒泡就是从最深的节点开始逐步向上传播的事件

>react 子父组件通信

1，父组件可以向子组件传递props，props中带有初始化子组件的数据，还有回调函数
2，子组件的state发生变化时，在子组件的事件处理函数中，手动触发父函数传递进来的回调函数，同时时将子组件的数据传递回去


>DOCTYPE的作用

主要作用是告诉浏览器的解析器使用哪种HTML规范或者XHTML规范来解析页面。

>v-if和v-show 

相同点：v-if与v-show都可以动态控制dom元素显示隐藏
不同点：v-if显示隐藏是将dom元素整个添加或删除，而v-show隐藏则是为该元素添加css--display:none，dom元素还在。

>es6新特性

`let`和`const`
let 块级作用域 const定义常量

`箭头函数`
ES6中的函数定义不再使用关键字function()，而是利用了()=>来进行定义，默认定义了this

`for of循环`
对带有迭代器的进行遍历

`async、await`
　　使用 async/await, 搭配promise,可以通过编写形似同步的代码来处理异步流程, 提高代码的简洁性和可读性
　　async 用于申明一个 function 是异步的，而 await 用于等待一个异步方法执行完成

`... 展开运算符`

>http

>redux

首先由view dispatch拦截action，然后执行对应reducer并更新到store中，最终views会根据store数据的改变执行界面的刷新渲染操作。

>promise
   
对象的状态不受外界影响，promise对象代表一个异步操作，有三种状态，pending（进行中）、fulfilled（已成功）、rejected（已失败）。只有异步操作的结果，可以决定当前是哪一种状态，
Promise 对象的 then 方法接受两个参数：
promise.all

>em

 自身fontsize

>从输入URL到页面加载发生了什么？

1、浏览器的地址栏输入URL并按下回车。
2、浏览器查找当前URL是否存在缓存，并比较缓存是否过期。
3、DNS解析URL对应的IP。
4、根据IP建立TCP连接（三次握手）。
5、HTTP发起请求。
6、服务器处理请求，浏览器接收HTTP响应。
7、渲染页面，构建DOM树。
8、关闭TCP连接（四次挥手）。

>原型原型链

   每一个构造函数都拥有一个prototype属性，这个属性指向一个对象，也就是原型对象。当使用这个构造函数创建实例的时候，prototype属性指向的原型对象就成为实例的原型对象。
原型对象默认拥有一个constructor属性，指向指向它的那个构造函数（也就是说构造函数和原型对象是互相指向的关系）。
每个对象都拥有一个隐藏的属性[[prototype]]，指向它的原型对象，这个属性可以通过

Object.getPrototypeOf(obj) 或 obj.__proto__ 来访问。
实际上，构造函数的prototype属性与它创建的实例对象的[[prototype]]属性指向的是同一个对象，即 对象.__proto__ === 函数.prototype 。
如上文所述，原型对象就是用来存放实例中共有的那部分属性。
在JavaScript中，所有的对象都是由它的原型对象继承而来，反之，所有的对象都可以作为原型对象存在。
访问对象的属性时，JavaScript会首先在对象自身的属性内查找，若没有找到，则会跳转到该对象的原型对象中查找。

> ie低版本兼容bug
   
   1.opacity 不识别
   2.双边距问题
   3.最小高度bug

> 判断一个变量是数组还是对象

Object.prototype.toString.call()方法可以精准判断变量类型

>html5的新特性

1.添加了用于媒介回放的 <video>，<audio> 元素
2.添加了语义标签譬如 header、footer、nav 等等元素 

>CSS3的新特性

1.媒体查询
2.选择器
3.圆角

