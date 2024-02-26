---
type: Code_Card
date_creation: 2024-01-18
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请完善下面的内容，使得 `df` 只含有原来相同年份数据的均值，例如：
```csv
年份,数值
2001,12
2001,14
2002,10
2002,14
```
变为
```csv
年份,数值
2001,13
2002,12
```
代码：
```python
df = df.________.reset_index()
```
Back: 
```
groupby("年份").means()
```
Addition: 
这个案例比较常用，应该记住。
<!--ID: 1705568896423-->
END