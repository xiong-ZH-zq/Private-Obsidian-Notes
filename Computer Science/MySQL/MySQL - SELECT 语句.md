---
type: code_note
---
# MySQL SELECT 语句

## SELECT 语句基本用法
### 基本用法
```mysql
-- 基本的 SELECT 语句结构：
-- SELECT 字段1, 字段2, ... FROM 表名
SELECT 1+1, 3*2 FROM DUAL;
```
注意这里面的 `DUAL` 是关键字，表示伪表.

选取全部内容：
```mysql
SELECT * FROM mydata;
```

### 列的别名
如果我们想重新给一列起一个别名，可以如下操作：
```mysql
SELECT first_name AS fname FROM mydata;
```
需要注意的是，`AS` 可以省略，并且整个数据表也可以起别名.

如果别名有空格，可以用 `""` 空起来，但是不能使用单引号，因为这个方面的规范在 Oracle 和 MySQL 里就有不同.

### 去除重复行
我们接下来使用 SELECT 取出不重复的行. 我们实际上加一个 `DISTINCT` 即可.

```mysql
SELECT DISTINCT first_name AS fname FROM mydata;
```


### 空值问题
1. null 本身不等于 0, '' 和 'null' .
2. 如果空值参与运算，结果也一定为空.
3. 可以引入 `IFNULL` 函数解决上述问题.

### 着重号
如果我们的表名和关键字是一致的，例如 `order` ，但是我们想选中，我们可以用着重号包住.

```mysql
SELECT * FROM `order`;
```

此时即可选中我们想要的 `order` 表.

### 显示表结构
直接使用 `describe` 可以显示表的结构.

```mysql
DESCRIBE employees;
```

写 `DESC` 一致，基本就是缩写.

## 使用 WHERE 过滤数据
`WHERE` 为 `SELECT` 加上了条件，使得 `SELECT` 选取数据时能有效过滤数据.

例如，现在我想在 `employees` 表当中选取名为 `Jack` 的所有员工数据，可以有如下代码：
```mysql
SELECT * FROM employees WHERE first_name = 'Jack';
```
