<script>
	/*
click 事件
注解： input组件 和 switch组件目前并不支持 click 事件，请使用 change 或 input 事件代替。
	type: click；
	target: 触发事件的目标组件；
	timestamp: 事件触发的时间戳。
 appear 事件被绑定到某个滚动区内的组件上，当组件可见时该事件触发。
	type: appear；
	target: 触发事件的目标组件；
	timestamp: 事件触发的时间戳；
	direction: 屏幕滚动时的滚动方向，up 或 down。
disappear 事件被绑定到某个滚动区内的组件上，该事件将在组件滚动出视口，消失时触发。
	type: disappear；
	target: 触发事件的目标组件；
	timestamp: 事件触发的时间戳；
	direction: 屏幕滚动时的滚动方向，up 或 down。
	*/
	/*
append
append属性没有做数据绑定的工作。它不会改变最终的渲染效果。
但是此属性确定是以一整棵树或子节点的方式添加。
append 有两个关键属性，tree 和 node.
<template>
  <container>
    <container id="world" append="tree">
      <text>Hello World!</text>
    </container>
    <container id="weex" append="node">
      <text>Hello Weex!</text>
    </container>
  </container>
</template>
	tree:等待其所有子元素渲染完成，才完全全部渲染。
	node:只完成自身的渲染就会被呈现在页面上，其子元素渲染完成一个展示一个。
	node渲染方式会使第一次绘画的速度比tree快些，但是总体的渲染时间可能比 append="tree" 长些。
	默认情况下，元素的呈现为 node 模式，只要元素是 tree的渲染方式，其子元素都将已 tree模式渲染。
	*/
</script>