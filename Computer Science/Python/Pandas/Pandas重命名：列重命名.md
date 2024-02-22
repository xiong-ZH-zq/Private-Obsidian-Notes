---
type: Code_Card
date_creation: 2024-01-18
code_language: python
---
TARGET DECK: Code::python::pandas

START
Programming
将如下的 `df` 中的 `info` 列名重命名为 `foo` （就地操作）：
```python
import pandas as pd
# df : pd.DataFrame
df.______
```
Back: 
```
rename(columns={"info":"foo"},inplace=True)
```
Addition:
这个部分就是字典一一对应修改的一个应用。
<!--ID: 1705570360943-->
END