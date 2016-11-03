<script>
	/*
安装weex:npm install -g weex-toolkit
weex tech_list.we//打开文件
weex --version//查看版本
weex tech_list.we --qr//终端二维码Weex Playground App查看
	*/
	/*组件封装
创建一个名为foo.we的文件，<foo>就是组件名，包含<template>，<style> 和 <script>
直接用<foo>标签即可, 注意这里bar.we和foo.we是在同目录下
<!-- bar.we -->
<template>
  <foo title="..." image="..."></foo>
</template>
	*//*组件嵌套
封装好的组件也支持嵌套
<!-- main.we -->
<template>
  <bar list="{{list}}"></bar>
</template>
main.we嵌套了<bar>, <foo-list>嵌套了<foo>。
	*//*
每个封装好的组件都有一个独立的<style>
如果子组件有 id 属性，可以通过this.$vm(id)来访问子组件的上下文，并可以通过this.$el(id)来找节点。
	*//*scroller
scroller是一个竖直的，可以容纳多个排成一列的子组件的滚动器。 如果子组件的总高度高于其本身，那么所有的子组件都可滚动。
注意: 可以当作根元素或者嵌套元素使用。此组件的滚动方向是列的形式,不可更改.
子组件:这类组件支持任意类型的weex组件作为其自组件。
属性:scrollDirection: 定义子组件的滚动方向, horizontal 或者 vertical。 仅包括 公共属性.
样式:支持flexbox相关样式 支持box model相关样式 支持position相关样式  支持opacity, background-color等.
//事件
支持click/appear / disappear事件
	*/
</script>