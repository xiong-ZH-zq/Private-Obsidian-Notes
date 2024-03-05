---
type: Code_Card
date_creation: 2024-02-07
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请补全下面的代码，使得其输出 `df` 中各列的缺失值数量.
```python
import pandas as pd
# df 定义过程省略
___________
```
Back: 
```
df.isnull().sum()
```
Addition: 
输出结果类似如下的内容：
```
c1 2 
c2 1 
dtype: int64
```
如果继续求和，输出的结果将会是 `3` .
<!--ID: 1707316080201-->
END