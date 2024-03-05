---
type: Code_Card
date_creation: 2024-01-16
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请补全下列的 Python 代码，从而将 person 按照 id 列进行排序。（就地操作，其余为默认）
```python
import pandas as pd
# person: pd.Dataframe
person.______
```
Back: 
```
sort_values(by="id",inplace=True)
```
Addition: 
除了这些参数之外，其余的参数还有："ascending" ，表示升序还是降序。当有多个参数列的时候，可以传入一个列表，例如 `["id"]` .
<!--ID: 1705394377031-->
END