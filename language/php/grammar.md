## 语法

### setcookie()

以下代码的输出是什么？

```php
setcookie("test", "value");
echo $_COOKIE["test"];
```

第一次访问输出空白，第二次才会输出 value。

原理：

`setcookie()` 函数向客户端发送一个 HTTP cookie。

cookie 是由服务器发送到浏览器的变量。cookie 通常是服务器嵌入到用户计算机中的小文本文件。每当计算机通过浏览器请求一个页面，就会发送这个 cookie。

所以，第一次访问发送 cookie，第二次访问 cookie 到达服务端。

### array_merge() 和 + 的区别？

#### array_merge()

1. 合并的数组中有**相同的字符串**键名，则后面的值覆盖前面的值
2. 合并的数组中有相同的数字键名，则后面的值不覆盖前面的值，而是依次附加到后面
3. 如果只有一个数组，并且该数组是数字索引的，则键名会以连续方式重新索引

```php
// 相同键名的处理方式
$arr1 = array("color" => "red", 2, 4);
$arr2 = array("a", "b", "color" => "green");
$result = array_merge($arr1, $arr2);
dump($result);
/*
array(5) {
    ["color"] => string(5) "green"
    [0] => int(2),
    [1] => int(4),
    [2] => string(1) "a"
    [3] => string(1) "b"
}
*/
```

```php
// 数字索引的处理方式
$arr1 = array();
$arr2 = array(1 => "a", 2 => "b");
$result = array_merge($arr1, $arr2);
dump($result);
/*
array(5) {
    [0] => string(1) "a"
    [1] => string(1) "b"
}
*/
```

#### array + array

`array+array` 是数组的联合运算。

1. 如果合并的数组中有相同的字符串键名，则取最先出现的值而把后面拥有相同键名的那些值“抛弃”
2. 如果合并的数组中有相同的数字键名，则取最先出现的值而把后面拥有相同键名的那些值“抛弃”
3. 如果只有一个数组，并且该数组是数字索引的，则键名会以连续方式重新索引（与 `array_merge()` 方法相同）

```php
$arr1 = array("color" => "red", 2, 4);
$arr2 = array("a", "b", "color" => "green");
$result = $arr1 + $arr2;
dump($result);
/*
array(5) {
    ["color"] => string(5) "red"
    [0] => int(2),
    [1] => int(4),
}
*/
```

### @ 的作用是什么？

PHP 支持一个错误控制运算符 `@`。当将其放置在一个 PHP 表达式之前，该表达式可能产生的任何错误信息都被忽略掉。

### & 的作用是什么？

[引用传递](http://php.net/manual/zh/language.references.pass.php)

- 变量的引用
- 函数的引用
