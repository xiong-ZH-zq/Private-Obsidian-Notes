---
type: Code_Card
date_creation: 2024-02-08
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
假设 `data` 中的 `Date` 列已经转换为日期格式，请输出每个行对应的日期中日的部分.
```python
import pandas as pd
_____
```
Back: 
```
data['Date'].dt.day
```
Addition: 
以上的输出将会是如下格式的内容：
```
0         2
1         4
2         5
3         8
4         9
         ..
23407    28
23408    28
23409    28
23410    29
23411    30
```
需要注意的一点是，此时输出的内容格式改变为 `int32` 了.
<!--ID: 1707400442031-->
END