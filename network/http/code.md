## HTTP 状态码

### 常见的 HTTP 响应状态码

- 1xx：请求的信息正在处理
    - 100 continue：目前为止都正常，客户端继续请求或忽略这个响应（客户端应用程序有一个实体的主体部分要发送给服务器，但发送前要查看一下服务器是否会接受这个实体）
- 2xx：成功
    - 200 ok
    - 204 No Content：返回报文不包含实体的主体部分
    - 206 Partial Content：客户端进行了**范围请求**，响应豹纹包含由 `Content-Range` 指定范围的实体的内容
- 3xx：重定向
    - 301 Moved Permanently：永久性重定向（资源已经被移除）
    - 302 Found：临时重定向
    - 303 See Other：同 302，但要求客户端用 GET 获取资源
    - 304 Not Modified：如果请求报文首部包含一些条件，若不满足条件，返回 304。条件如下：
        - If-Match
        - If-Modified-Since
        - If-None-Match
        - If-Range
        - If-Unmodified-Since
    - 307 Temporary Redirect：临时重定向，与 302 类似，但 307 不会把重定向的 POST 方法改成 GET 方法
- 4xx：客户端错误
    - 400 Bad Request：请求报文中存在语法错误
    - 401 Unauthorized：请求需要有认证信息（BASIC 认证，DIGEST 认证），无认证信息或用户认证失败
    - 403 Forbidden：请求被拒绝
    - 404 Not Found
    - 405 Method Not Allowed：请求方法不被允许
- 5xx：服务器错误
    - 500 Internal Server Error：服务器正在执行请求时发生错误
    - 503 Service Unavailable：服务器暂时处于超负载或正在进行停机维护，无法处理请求
    
### 302 表示什么？

表示临时重定向。

服务器返回的头部信息会包含一个 Location 字段，内容是重定向的 URL。