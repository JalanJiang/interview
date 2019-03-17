## Shell

### 查看系统当前进程的连接数

```
netstat -an | grep ESTABLISHED | wc -l
```

### 找出大小超过 10MB 的文件

```
# 在当前目录寻找
find ./ -type f -size +10240k
```

### 找出 90 天内未被访问过的文件

```
find ./ \! -atime -90
```

### 找出 120 天之前被修改过的文件

```
find ./ -mtime +120
```

### 根据名称查找文件并删除

```
find / -name core -exec rm {} \;
```

### 