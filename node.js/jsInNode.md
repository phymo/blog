## 

## EcmaScript

## 核心模块

- require加载模块：`var fs = require('fs')`

1. fs 文件系统
2. http 服务
3. path 路径
4. os 操作系统
5. ...  

## 模块系统

1. 多文件执行（模块化）

2. 模块有三种

   - 具名的核心模块

   - 用户自己编写的文件模块

     - require 加载模块

     - 相对路径必须加 `./`

     - 可以省略后缀名。

     - Node中没有全局作用域，只有模块作用域

       - 模块之间怎么通信：模块的导出

         ``` js
         //require 可以加载模块并执行代码
         //也可以拿到加载模块导出的接口对象,exports是一个对象
         exports.foo= 'hello';
         ```
