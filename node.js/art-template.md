## 子模版

{{ include './header.html'}}

## 模板继承

``` 
​	{{ block 'content'}}

	<h1> 默认内容</h1>

	{{/block}}
```

引用模板：

`{{extend './layout.html' }}`

