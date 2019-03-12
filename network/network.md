## 计算机网络

### 在浏览器地址栏输入一个URL后回车，背后会进行哪些技术步骤？

- 识别 URL 是否合法
- DNS 解析，获得域名对应的 IP 地址
    - 先检查内存里的 DNS Cache
    - 检查本地硬盘里的 host 文件
    - 请求自己的 DNS 服务器 `8.8.8.8`
        - 将请求打包：收件人地址 `8.8.8.8`，寄件人地址 `1.1.1.1`
        - UDP 进行请求处理
- 发送 HTTP 请求，建立 TCP 连接（三次握手）
- 服务器处理请求并返回 HTTP 报文
- 浏览器解析渲染页面
- 连接结束

## 参考资料

- [前端经典面试题: 从输入URL到页面加载发生了什么？](https://segmentfault.com/a/1190000006879700)