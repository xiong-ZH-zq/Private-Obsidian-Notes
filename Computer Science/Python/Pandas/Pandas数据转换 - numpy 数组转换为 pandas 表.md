---
type: Code_Card
date_creation: 2024-02-08
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请将以下代码补全，使得 `data` 转化为一个 pandas 数据框，列名为 `name` ：
```python
import pandas as pd
import numpy as np
# data 为 numpy 数组
data = _______
```
Back: 
```python
pd.DataFrame(data,columns=['name'])
```
Addition: 
`pandas` 中对 `numpy` 支持主要体现于数据转换这个上面.
<!--ID: 1707398213160-->
END