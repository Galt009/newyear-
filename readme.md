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
