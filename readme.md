# 使用vue的步骤
1.导入Vue的包  
2.创建一个Vue的实例  

```
<div id="app"> //V
  <p>{{ msg }}</p>  
</div>
```  
3.当我们导入包之后，在浏览器的内存中，就多了一个 Vue 构造函数
```
<script>
   var vm = new Vue({ //VM
      el: '#app',
      data: {
         msg: 'hello' // M
      }
   })
```
# 事件修饰符
```
<div class="inner" @click="divHandler">
   <input type="button" value="点击" @click.stop="btnHandler">
</div>
```
* .stop 阻止冒泡
* .prevent 阻止默认事件
* .capture 添加事件侦听器时使用事件捕获模式
* .self 只当事件在该元素本身（比如不是子元素）触发时触发回调
* .once 事件只触发一次
# 双向数据绑定
v-bind 只能实现数据的单向绑定，从 M 自动绑定到 V，无法实现数据的双向绑定  
使用 v-model 指令，可以实现表单元素和 Model 中数据的双向数据绑定  
v-model 只能运用在表单元素中  
input(radio, text, address, email...) select checkbox textraea
# 属性绑定（样式）
* 数组  
   ```
   <h1 :class="['thin', 'italic']">xxxx</h1>
   ```
* 三元表达式  
   ```
   <h1 :class="['thin', 'italic', flag?'active':'']">xxxx</h1>
   ```
* 在数组中使用对象来代替三元表达式  
   ```
   <h1 :class="['thin', 'italic', {'active':flag}]">xxxx</h1>
   ```
* 对象
   ```
   <h1 :class={red: true, thin: true}>xxxx</h1>
   ```
# 内联样式
*  ```
   <h1 :style=red>xxxx</h1>
   data里：
      data: {
         red: {color:'red'}
      }
   ```
# v-for循环的四种用法
* 普通数组
* 对象数组
* 对象
* 迭代数字  

注意事项：
* key属性只能使用 number 或 string
* 必须使用 v-bind 属性绑定的形式，指定key的值
* 在组件中，使用v-for循环的时候，或则在一些特殊情况中，如果v-for有问题，必须只当唯一的 字符串/数字 类型 :key 值
# v-if 和 v-show
```
<h3 v-if="flag">xxx</h3>
<h3 v-show="flag">xxx</h3>
data: {
   flag: true
}
```
v-if 有较高的切换新能消耗（每次都会重新删除或创建元素）  
v-show 有较高的初始喧嚷消耗（每次不会重新进行DOM的删除和创建操作，只是切换了元素的 display:none 样式）  
如果元素涉及到频繁的切换，最好不要使用v-if，而是推荐使用 v-show  
如果元素可能永远也不会被显示出来被用户看到，则推荐使用 v-if 
