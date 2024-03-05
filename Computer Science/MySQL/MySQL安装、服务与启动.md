---
type: code_note
---

## 启动服务和停止服务
启动服务的命令行：
```shell
net start mysql服务名
```
其中的 mysql 服务名根据不同的版本有不同的服务名，例如 8.0 版本就是 mysql80 ，这个地方需要注意。
关闭和开启类似：
```shell
net stop mysql服务名
```

## MySQL登录
### 明文登录指令
现在考虑登录问题，如果我们现在需要以 root 用户的身份登录，并且密码是 `abc123` ，那么密码明文登录的指令就是：
```shell
mysql -uroot -pabc123
```
注意 `-u` 和 `-p` 后面不能有空格，如果不想明文，可以直接写 `-p` ，从而输入密码时就有混淆符号。

如果有多个版本的 MySQL ，那么可以指定版本（或者说是端口），例如 5.7 版本的端口为 13306 ，那么就可以写为：
```shell
mysql -uroot -P13306 -p
```
如果还要突出显示为本地服务器，那么就有：
```shell
mysql -uroot -P13306 -h localhost -p
```

## 数据库查看
### 显示数据库
首先，接下来的语句都需要以分号结束，不然就会出问题（它会将多个命令认为成一个）。
显示当前有的数据库：
```mysql
show databases;
```
刚安装时，结果应该是如下的表格：
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```

### 创建、查看数据库
创建一个名为 `my_data` 的数据库的命令：
```mysql
create database my_data;
```

使用数据库的方法是使用 `use` 命令：
```mysql
use my_data;
-- 如果成功则会提示 database changed
```

### 建立、查看表
查看表的命令依然是 `show` ：
```mysql

```