---
type: Code_Card
date_creation: 2024-01-16
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请完善如下的 Python 代码，对 person 这个数据框的 "email" 列进行去重，操作为就地操作。
```python
import pandas as pd
# person: pd.DataFrame
person.______
```
Back: 
```
drop_duplicates(subset=["email"],inplace=True)
```
Addition: 
参数还有 `keep` ，可以选择  `first` ， `last` 和 `False` ，其中 `False` 表明出现重复就全去掉。
<!--ID: 1705395043191-->
END