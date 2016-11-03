<script>
  /*
当客户端接收到JS Bundle时，它能用被客户端中的JS引擎用于管理Native渲染;API调用和用户交互.
  */
/*工作流
Weex we 文件 --------------前端(we源码)
↓ (转换) ------------------前端(构建过程)
JS Bundle -----------------前端(JS Bundle代码)
↓ (部署) ------------------服务器
在服务器上的JS bundle  ----服务器
↓ (编译) ------------------ 客户端(JS引擎)
虚拟 DOM 树 --------------- 客户端(Weex JS Framework)
↓ (渲染) ------------------ 客户端(渲染引擎)
Native视图 ---------------  客户端(渲染引擎)
*//*
Transformer（转换器): 一个Node JS工具， 转换Weex源码为JS Bundle
Weex JS Framework(JS框架): 运行于客户端的的JS框架，管理着Weex实例的运行。
Weex实例由JS Bundle创建并构建起虚拟DOM树. 
它发送/接受 Native 渲染层产生的系统调用，从而间接的响应用户交互。
Native引擎: 在不同的端上，有着不同的实现: iOS/Android/HTML5. 
他们有着共同的组件设计, 模块API 和渲染效果，能配合同样的 JS Framework 和 JS Bundle工作。
*//*转换器转换Weex源码为JS Bundle分三步
1、转换 <template> 为类JSON的树状数据结构, 转换数据绑定为返回数据的函数原型.
<foo a="{{x}}" b="1"></foo>
==》{type: "foo", attr: {a: function () {return this.x}, b: 1}}.
2、转换 <style> 为类JSON的树状数据结构.
.classname {name: value;} 将转换为 {classname: {name: value}}.
3、 上面两部分的内容和 <script> 中的内容结合成一个JavaScript AMD 模块.
转换器还会做一些额外的事情: 合并Bundle ,添加引导函数，配置外部数据等
*//*
大部分Weex工具最终输出的JS Bundle格式都经过了Webpack的二次处理
*//*JS Framework
JS Framework在初始化阶段被原生JavaScript引擎运行. 
它提供被每个JS Bundle调用的 define() 和 bootstrap() 函数. 
一旦JS Bundle从服务器下载后，这些函数就会执行. 
define() 函数以注册模块;
bootstrap()会编译主要的模块为虚拟DOM，并发送渲染指令给Native .
*//*JS 和 Native 的沟通
1、callNative 是一个由native代码实现的函数, 它被JS代码调用并向native发送指令
2、callJS 是一个由JS实现的函数, 它用于Native向JS发送指令. 这些指令由用户交互和Native的回调函数组成.
*//*Native 渲染引擎
Native 渲染引擎提供客户端组件和模块.
Component(组件) 在屏幕内可见，有特定行为. 能被配置不同的属性和样式,能响应用户交互.
常见的组件:<text><image>
Module(模块) 是一组能被JS Framework调用的API. 其中的一些能以异步的方式调用JS Framework.
在Weex实例运行期间,Native渲染引擎将接收各种各样不同模块的API调用,用于创建或更新组件外观.
当用户交互或模块回调时，callJS()会由JS Framework调用. 这样的循环往复将从Weex实例初始化到销毁一直持续. 
从Javascript中调用Native
[JS Framework]
↓ callNative
模块 APIs
  渲染 -> 模块显示
  其他功能
[Native 渲染引擎]
从Native中调用Javascript

[Native 渲染引擎]
模块 APIs 回调
用户交互
↓ callJS
[JS ]
渲染流Framework程
*//*
虚拟DOM.
构造树结构. 分析虚拟DOM JSON数据以构造渲染树(RT).
添加样式. 为渲染树的各个节点添加样式.
创建视图. 为渲染树各个节点创建Native视图.
绑定事件. 为Native视图绑定事件.
CSS布局. 使用 css-layout 来计算各个视图的布局.
更新视窗(Frame). 采用上一步的计算结果来更新视窗中各个视图的最终布局位置.

最终页面呈现.
在Weex HTML5环境下 CSS 布局 and 更新视窗 由浏览器引擎(例如webkit)实现.
*/
</script>