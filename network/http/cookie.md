## Cookie

### Cookie 和 Session 有什么区别？

1. 数据存放位置不同：cookie 数据存放在客户的浏览器上，session 数据放在服务器上。
2. 安全程度不同：cookie不是很安全，别人可以分析存放在本地的 cookie 并进行 cookie 欺骗，考虑到安全应当使用 session
3. 性能使用程度不同：session 会在一定时间内保存在服务器上。当访问增多，会比较占用你服务器的性能,考虑到减轻服务器性能方面，应当使用cookie
4. 数据存储大小不同：单个 cookie 保存的数据不能超过 4K，很多浏览器都限制一个站点最多保存 20 个 cookie，而 session 则存储与服务端，浏览器对其没有限制

### 如果 Cookie 被禁用怎么办？

使用 Web storage：

- localStorage
    - 一直存储在本地，数据存储是永久的，除非用户或程序对其进行删除操作
- sessionStorage
    - 在会话期内有效，数据在浏览器关闭后自动删除
