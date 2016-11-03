<script>
/*
在组件的方法中通过 this （Vm）上下文访问这些 API
*//*$(id)
	使用$vm代替
*//*$el(id)返回对应 id 的元素对象的引用。
	id 只能保证是当前（页面）组件中是唯一的，需要寻找父组件或子组件，利用组件间的通信模式实现。
*//*$vm(id)返回对应 id 的 vm 对象引用。
*//*$getConfig()获取当前全局环境变量和配置信息。
config (object): 配置对象；
bundleUrl (string): bundle 的 url；
debug (boolean): 是否是调试模式；
env (object): 环境对象；
weexVersion (string): Weex sdk 版本；
appName (string): 应用名字；
appVersion (string): 应用版本；
platform (string): 平台信息，是 iOS、Android 还是 Web；
osVersion (string): 系统版本；
deviceModel (string): 设备型号 （仅原生应用）；
deviceWidth (number): 设备宽度，默认为 750；
deviceHeight (number): 设备高度。
*//*$call(module, method, ...args)//使用require('@weex-module/module')[method](...args)替换
*/
/*
<script>标签支持在页面的顶级组件中通过 type 属性定义两种配置。
type="data": 配置初始化数据，这里定义的数据会覆盖定义在<script>中的数据；
type="config": 定义配置项。
<script type="data"> (可选) 定义初始化数据 
<script type="config">(可选) 定义配置项 
//定义初始化数据
Weex 允许<script type="data"> 标签定义初始化数据,定义的数据将完全取代默认的 <script> 标签中定义的数据。
<script type="data">
  module.exports = {
      title: 'Alibaba',
      date: new Date().toLocaleString()
  }
//配置项
Weex 也允许我们通过 <script type="config"> 定义一些配置项，仅只支持配置 downgrade。
	downgrade.osVersion
	downgrade.appVersion
	downgrade.weexVersion
	downgrade.deviceModel
*/

</script>