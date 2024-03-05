---
type: Code_Card
date_creation: 2024-02-07
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请补全下列的 pandas 代码，使得 `df` 每个缺失值补全为上一行对应列的值（如果为第一行则补全为 1），操作为就地操作.
```python
import pandas as pd
df.______
```
Back: 
```
ffill().fillna(1,inplace=True)
```
Addition: 
就地操作时只需要在最后的操作加上就地即可，如果在 `ffill` 中加上了 `inplace=True` 请重来.
<!--ID: 1707317610230-->
END