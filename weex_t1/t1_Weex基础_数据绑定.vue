<script>
	/*
Weex使用mustache的语法({{…}})来对<template>中的模板和<script>里的数据进行绑定. 
一旦数据额模板绑定了, 数据上的修改会实时的在模板内容中生效.
可以通过.符号来绑定数据结构中的字段
	*//*
In-template 表达式//进行数据绑定时, Weex支持一些简单的javascript表达式

每个绑定只能包含单个表达式，在模板里实现更多的逻辑判断,使用computed.

data 和 methods 不能有重复的字段. 因为在执行的上下文中 – this, 能同时指向这两者.

组件的样式能够通过style属性进行绑定，也可以通过class进行数据绑定

以on...开头的属性的值就是对应进行事件处理的函数名. 不需要添加mustache语法中的大括号或者函数调用时的圆括号.

if 属性能够通过true/false值控制组建是否显示.

Weex通过repeat属性来生成列表


当你修改 data 中的数组时，在写法上会受到一定的限制，具体如下
直接通过 index 修改数组的某个项目 (如 vm.items[0] = {};) 是不会触发视图自动更新的。
数组的原型上提供了一个额外的方法：$set(index, item).与vm.items[0]作用相同，但会自动触发视图更新
example1.items.$set(0, { childMsg: 'Changed!’})

直接通过修改 length 来改变数组长度 (如 vm.items.length = 0) 也是不会触发视图自动更新的。
直接赋值一个新的空数组把旧的替换掉。和 example2.items.length = 0 作用相同，但会自动触发视图更新
example2.items = []
*//*
键名按照连接符的方式进行命名, 键值可以是数字(默认的单位是px).
屏幕的宽度统一为750像素, 不同屏幕会按照比例转化为这一尺寸.
标准CSS支持很多样式选择器, 但Weex目前只支持单个类的选择器.
标准CSS支持很多的长度单位,Weex目前只支持像素,并且px在样式中可以忽略不写,
子元素的样式不会继承自父元素.
标准CSS包含了非常多的样式属性, 但Weex只支持了其中的一部分, 包括盒模型,flexbox,position等布局属性. 以及font-size, color等样式.
*//*
<template>
  <container style="flex-direction: row;">
  	<text style="font-size: {{title.size}}">{{title.value}}</text>
  	<text>{{firstName + ' ' + lastName}}</text>
    <text>{{fullName}}</text>
    <text onclick="changeName"></text>
    <image src="..." if="{{shown}}"></image>
  </container>
</template>

<script>
  module.exports = {
    data: {
      firstName: 'John',
      lastName: 'Smith',
      title: {
        size: 48,
        value: 'Alibaba Weex Team'
      }
    },
    computed: {
      fullName: {
        get: function() {
          return this.firstName + ' ' + this.lastName
        },

        set: function(v) {
          var s = v.split(' ')
          this.firstName = s[0]
          this.lastName = s[1]
        }
      }
    },
    methods: {
      changeName: function() {
        this.fullName = 'Terry King'
      }
    }
  }
	*/
</script>