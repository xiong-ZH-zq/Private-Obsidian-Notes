---
type: Code_Card
date_creation: 2024-01-21
code_language: mysql
---

TARGET DECK: Code::MySQL

START
Programming
现在有如下信息，请进行 MySQL 明文登录：
- 账号：foo
- 密码：a123456
补全如下登录命令：
```shell
mysql _____ _____
```
Back: 
```
-ufoo -pa123456
```
Addition:
这种明文登录的坏处在于会直接在命令行窗口暴露用户名和密码，影响数据库的安全性。一般而言最好 `-p` 后不加东西.
<!--ID: 1705844669508-->
END