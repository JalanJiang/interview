## SQL 注入

### 什么是 SQL 注入？

通过把 SQL 命令插入到 Web 表单提交或输入域名或页面请求的查询字符串，最终达到欺骗服务器**执行恶意的SQL命令**。

即：提交恶意 SQL 命令并欺骗服务器执行。

### SQL 漏洞存在的原因是什么？

拼接 SQL 参数。也就是将用于输入的查询参数，直接拼接在 SQL 语句中，导致了 SQL 注入漏洞。

将用户输入的字符串，当成了 “sql语句” 来执行。

### SQL 的防御方式？

#### 预处理查询（Prepared Statements）

```php
$mysqli = new mysqli("example.com", "user", "password", "database");
# mysqli:prepare() 实现
$stmt = $mysqli->prepare("SELECT id, label FROM test WHERE id = ?");
$stmt->bind_param(1, $city);
$stmt->execute();
$res = $stmt->get_result();
$row = $res->fetch_assoc();
```

PDO 方式

```php
$pdo = new PDO("mysql:host=localhost;dbname=test;",'root','pwd');
$pdo->setAttribute(PDO::ATTR_EMULATE_PREPARES,false);
$pdo->exec('set names utf8');
$id = '0 or 1 =1 order by id desc';
$sql = "select * from article where id = ?";
$statement = $pdo->prepare($sql);
$statement->bindParam(1, $id);
$statement->execute();
```

使用 prepared statements（预处理语句）和参数化的查询，可以有效的防止sql注入。

#### mysql_real_escape_string()

#### 魔术引用 

`addslashes()`

## 参考资料

- [php操作mysql防止sql注入(合集)](https://segmentfault.com/a/1190000008117968)


