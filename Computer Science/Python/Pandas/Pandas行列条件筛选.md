---
type: Code_Card
date_creation: 2024-01-16
code_language: python
---
TARGET DECK: Code::python::pandas

START
Programming
[595. 大的国家 - 力扣（LeetCode）](https://leetcode.cn/problems/big-countries/description/)
完善如下的函数，使得其筛选出 world 当中 area 大于等于 300 或 population 大于等于 250 的行。
```python
import pandas as pd
def big_countries(world: pd.DataFrame) -> pd.DataFrame:
    return _____
```
Back: 
```
world[(world["area"]>=300)|(world["population"]>=250)]
```
Addition: 
此处使用的是或运算符 `|` ，这个在 C 语言当中是按位或，需要区分。
<!--ID: 1705398268414-->
END