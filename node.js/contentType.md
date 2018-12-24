

服务器端默认发送的数据 是utf-8的内容

但浏览器不知道是utf-8，会按照操作系统默认编码解析

中文操作系统默认为gbk

所以发送数据时要为浏览器指定编码

```js
res.setHeader('Content-type', 'text/plain; charset=utf-8') // text/html
res.end('hello 世界')
```

使用 fs.readFile 返回文件中的数据 如HTML文档，图片等

图片不需要指定编码