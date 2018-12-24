## IP地址和端口

### IP

- 计算机只有一个物理网卡，在同一个局域网中网卡地址是唯一的，网卡需要通过唯一的ip地址来进行定位。（IP地址解析域名，方便记忆）

### 端口

- 端口号用来定位具体的应用程序 （所有通过联网通信的软件都必须要有端口号）
- 客户端浏览器会自动生成端口
- 范围 0-65536
- 有些端口最好不要使用，已经默认使用了（如80，1，2，...）
- 开发时推荐使用3000，5000，8000，8080；（无意义）
- 上线部署网站时 使用默认端口号（:80）；
- 