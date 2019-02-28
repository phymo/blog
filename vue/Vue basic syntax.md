# 模板语法

1. {{msg}} ： 使用v-once， 一次性插值

2.  v-html : `<span v-html="rawHtml"></span>`(容易导致XSS攻击)

3. v-bind 指令-- 简写为：绑定HTML特性

   > 所有数据绑定都可以用Javascript表达式（单个表达式）

4. v-if 

5. v-for 

   ``` vue
   <ol>
       <li v-for="todo in todos">
       	{{ todo.text }}
       </li>
   </ol>	
   ```

6. ` v-on:click = "foo"` 简写为@click
7. `<input v-model="message">` 表单输入与应用状态双向绑定 

> `v-`表示指令，指令特性预期值为**单个js表达式**（v-for除外）

> 一些指令可以冒号后接参数 `v-bind:href="url"`

> 2.6.0之后支持动态参数`v-bind:[attrName]="url"` 动态参数预期会求出一个字符串

> 修饰符 `<form v-on:submit.prevent="onSubmit">`

# 组件化：

``` html
<div id="app">
    <ol>
        <todo-item
          v-for="item in items"
          :todo="item"
          :key="item.id" 
          />
    </ol> 
</div>
```

```vue
// 注册todo-items组件
vue.component('todo-item',{
	props:['todo'],
	template: '<li>{{ todo.text }}</li>
})

// 实例化
var app = new Vue({
	el: '#app',
	data: {
		items: [
			{ id: 0, text: 'sss'},
			{ id: 1, text: 'eee'}
			{ id: 2, text: 'gggg'}
		]
	}
})
```

# 生命周期 

beforeCreate, created, beforeMount, mounted, beforeDestroy, destroyed, beforeUpdate, updated