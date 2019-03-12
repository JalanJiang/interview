## CSRF 攻击

### 什么是 CSRF 攻击？

CSRF（Cross Site Request Forgery），中文是跨站点请求伪造。

CSRF 攻击者在用户已经登录目标网站之后，诱使用户访问一个攻击页面，利用目标网站对用户的信任，以用户身份在攻击页面对目标网站发起**伪造用户操作的请求**，达到攻击目的。

即：攻击者盗用了你的身份，以你的名义发送恶意请求。

### CSRF 如何防御？

1. 尽量使用 POST，限制 GET
    - GET 方法容易被用来做 CSRF 攻击，只要构造 URL 就可以轻易实现
    - POST 方法并非万无一失，攻击者只要构造一个 form 就可以，但需要在第三方页面完成，会增加暴露可能性
2. 浏览器 Cookie 策略
3. 增加验证码验证
4. Referer Check：检查请求是否来自合法的源
5. Anti CSRF Token：token 检测法，每次请求带上代表用户身份的 Token 令牌

## 参考资料

- [CSRF理解与防御](https://www.cnblogs.com/lsdb/p/9591399.html)