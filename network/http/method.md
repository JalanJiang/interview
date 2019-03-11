## HTTP 方法

### 常用的 HTTP 方法有哪些？

- GET
- POST
- PUT
- HEAD
- DELETE
- OPTIONS

### GET 和 POST 的区别有哪些？

1. GET 从服务器上获取资源；POST 向服务器发送数据
2. GET 数据在 URL 中传输；POST 将字段与对应值封存在请求实体中
3. GET 传输数据量小，URL 长度受限；POST 传输数据量大
4. GET 不安全，URL 可见；POST 比较安全（但不是绝对安全）
5. GET 仅支持 ASCII 字符；POST 支持标准字符集
6. GET 安全、幂等、可缓存；POST 不安全、不幂等、不可缓存