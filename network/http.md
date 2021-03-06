## HTTP

### 什么是 HTTP 协议

- 简称：超文本传输协议
- 是客户端和服务端之间数据**传输的格式规范**
- 是构建于 TCP/IP 协议之上的**应用层协议**
- 默认端口号：80
- HTTP 是**无连接状态**的

### HTTP 无状态是什么意思？

无状态：对于事务处理没有记忆能力。

解决方法：Session、Cookie

### HTTP 的特征有哪些？

- 无连接（限制每次连接只处理一个请求。服务器处理完客户的请求，并收到客户的应答后，即断开连接。采用这种方式可以节省传输时间。）
- 无状态
- 灵活
- 简单快捷
- 支持 客户/服务器 模式

## 参考资料

- [如何理解HTTP的无连接、短连接、长连接？](https://segmentfault.com/a/1190000015821798)