## 模块：http

- 职责：创建服务器

  + 加载http 核心模块：

    ```javascript
    var http = require('http'); //加载
    var server = http.createServer(); //创建 
    ```

- 服务器开启：

  ``` javascript
  server.on('request',function(){...}); //响应请求
  server.listen(3000, function(){});//绑定端口号启动服务器，回调写日志；
  ```

  + 关闭服务器： ctrl+c；

- 服务器响应：

  ```js
  server.on('request', function(request,response)){
      response.write('hello'); //write可以有多个，但必须end
      response.write('node.js'); //注意需重启服务器
      reponse.end();
  }
  ```

- 关闭服务器： ctrl+c；

- 根据不同的请求路径发送不同的响应结果

  ``` js
  server.on('request',function(req,res){
      //1. 获取请求路径
      // req.url 获取的是端口号之后的那一部分路径，也就是说所有url都已 / 开头
      var url = req.url;
      if(url === '/'){
          res.end('index page')
      } else if(url === '/'){
          res.end('login page')
      } else{
          res.end('404 not found!') 
       //注意相应数据必须是二进制数或者字符串，传对象或数组必须转换 JSON.stringify()
      }
  })
  ```

