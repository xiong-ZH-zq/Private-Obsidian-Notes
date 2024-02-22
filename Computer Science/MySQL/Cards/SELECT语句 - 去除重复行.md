---
type: Code_Card
date_creation: 2024-02-12
code_language: mysql
---

TARGET DECK: Code::MySQL

START
Programming
请使用 MySQL 取出表 `foo` 中列 `id` 的不重复内容.
Back: 
```mysql
SELECT DISTINCT id FROM foo;
```
Addition: 
`DISTINCT` 可以保证内容不重复. 类似于 Pandas 里面的 `drop_duplicates` .
<!--ID: 1707745180743-->
END