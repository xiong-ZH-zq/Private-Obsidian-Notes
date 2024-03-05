---
type: Code_Card
date_creation: 2024-02-06
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请完善下面的函数，使得 `df` 的 `foo` 列取根号乘十（numpy 取根号）.
```python
df_squared = df[['foo']]._______
```
Back: 
```
apply(lambda x: 10*np.sqrt(x),axis=1)
```
Addition: 
使用 `apply` 函数可以直接对列使用函数.
<!--ID: 1707230751714-->
END