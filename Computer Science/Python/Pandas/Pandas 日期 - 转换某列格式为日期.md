---
type: Code_Card
date_creation: 2024-02-08
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
现有 `df` 数据表，`day` 列包含日期，但是现在 pandas 认为它的数据类型为 `object` ，请将其转化为日期类型.
```python
import pandas as pd
# day列的日期形如：10/01/2024
df['day'] = ______
```
Back: 
```
pd.to_datetime(df['day'],format="%m/%d/%Y")
```
Addition: 
1. 注意以上的操作针对 `pd.Series` 
2. `%Y` 是针对年份全写的，在这个情境下不能使用小写 `%y` ，因为这个参数对应的是简写，例如 `10/01/24` . 对于更多的参数说明， pandas 服从官方库 datetime 的写法.
[Python Datetime 参数说明](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes)
<!--ID: 1707399128427-->
END