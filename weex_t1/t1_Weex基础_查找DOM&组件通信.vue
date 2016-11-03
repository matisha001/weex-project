<script>
	/*
weex中，可以通过在特定的节点上设置 id 属性，以此来唯一标识该节点。然后可以用 this.$(id)来找到该节点，以$scrollToElement() 为例。
<template>
    <container>
      <text id="top">Top</text>
      <container style="height: 10000; background-color: #999999;">
      </container>
      <text onclick="back2Top">Back to Top</text>
    </container>
  </template>
  <script>
    module.exports = {
      methods: {
        back2Top: function () {
          var top = this.$('top')
          this.$scrollToElement(top)   // both work
        }
      }
    }
	*//*
可以通过this.$vm(id) 方法可以访问子组件的上下文。
	*//*子组件向父组件通信
子组件能通过 this.$dispatch([String type], [Object detail]) 方法向父组件传送数据。
第一个参数代表通信事件名.第二个参数则是数据对象。

子组件的某个父组件通过$on([String type], [Function callback])
方法注册了一个相同名字的属性监听，那么callback函数将得到一个参数对象，并且参数对象的detail属性值为子组件传递出来的数据对象。
	*//*父组件向子组件通信
父组件能通过this.$([String id]) 获取子组件的上下文。
	*//*父组件向多个子组件通信
父组件能通过this.$broadcast([String type], [Object detail]) 方法像所有的子组件分发消息。
	*//*兄弟组件间通信
兄弟组件能通过父组件作为桥梁进行通信。
	*/
</script>