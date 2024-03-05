---
type: Code_Card
date_creation: 2024-02-06
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请补全下列的 pandas 相关代码，使得 `df` 的 `foo` 列可以根据 $f(1)=2$ ，$f(3)=7$ 的规则进行映射替换，其余保持不变.
```python
import pandas as pd
df[['foo']] = df[['foo']].________
```
Back: 
```
replace({1:2,3:7})
```
Addition: 
`replace` 函数可以根据字典进行数据映射，没有在字典当中的内容都将保持原状.
<!--ID: 1707231304992-->
END