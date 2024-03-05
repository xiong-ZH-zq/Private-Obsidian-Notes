---
type: code_note
---
## 隐式类型转换
对于 MySQL ，在计算的时候会进行和 JS 类似的隐式类型转换（但是没有 JS 那么阴间）.

例如，对于如下的计算，会将字符串自动转换为数值.
```mysql
SELECT 100+'1'
FROM DUAL;
```

但是如果字符串不能转换为数值，例如 `'a'` 这样的字符，就视为 0.

## 比较运算符
这里的运算符和 C 语言的基本一致（等于为一个等号），但是需要补充一个安全比较运算符 `<=>` .

首先就是比较运算符会出现隐式类型转换的问题，如果字符串和数值进行比较，则字符串看作 0 ，也就是说下面的结果将会是 1.
```mysql
SELECT 0='a' FROM DUAL;
```

然后，对于 `NULL` 值，只要 `NULL` 值参与判断，结果就是 `NULL` .  也就是说，如果在 WHERE 后面出现 `NULL` ，那么结果也将是 NULL ，从而 SELECT 无法选取到任何数据.

```mysql
SELECT * FROM employees WHERE salary != NULL;
```

例如上列代码，就不会选取任何数据.

此时的安全等于 `<=>` 在 NULL 情况下就发挥作用了，它与等号在一般情况下是一致的，在含有 NULL 的情况下则有不一样的功能.

```mysql
SELECT * FROM employees WHERE commission_pct <=> NULL;
```

上列代码表示如果 `commission_pct` 为空值，那么就选取.

## 关键字运算符
### 检验空值
虽然但是，在实际的操作流程当中，关键字运算符会更为常用，并且可读性也更强.

例如，对于不为 `NULL` ，可以写为

```mysql
SELECT * FROM employees WHERE commission_pct IS NOT NULL;
```

`NOT` 单用也可实现取反.

```mysql
SELECT * FROM employees WHERE NOT commission_pct <=> NULL;
```

但是还是更建议使用 `IS NOT NULL` 会更直观.

### 最大最小
`LEAST` 函数和 `GREATEST` 函数可以选取最小和最大的值（字符串内容按照字典序）.

### 边界
`BETWEEN 条件1 AND 条件2` 可以选取条件范围内的数据，**包含边界**. 需要注意的是条件 1 是下限，如果条件 1 比条件 2 还更大，那么就会出现没有选取任何数据的情况.

### 范围检测
如果我想取的是有限个离散值怎么办？实际上可以用 `IN` 来实现：

```mysql
SELECT * FROM employees WHERE commission_pct IN (0.3,0.4);
```

上列的代码检测了 commission_pct 的取值，如果为 0.3 或者 0.4 就选取.

### 模糊查询
使用 `LIKE` 可以使用模糊查询，例如查询包含字符 `'a'` 的内容.

```mysql
SELECT * FROM employees WHERE last_name LIKE "%a%";
```

注意上述内容使用了通配符，`%` 表示 0 个或多个字符. （数据库当中的通配符和文件系统的有所不同）

### 正则表达式
正则表达式直接看一个示例即可：

```mysql
SELECT * FROM employees WHERE last_name REGEXP '[A-Z]';
```

