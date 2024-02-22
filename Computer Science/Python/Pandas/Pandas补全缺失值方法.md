---
type: Code_Card
date_creation: 2024-01-18
code_language: python
---

TARGET DECK: Code::python::pandas

START
Programming
请补全下面的代码，使得 `df` 的 `info` 列用 0 补全缺失值（就地操作）：
```python
df["info"]._______
```
Back: 
```
fillna(0,inplace=True)
```
Addition:
使用 `fillna` 时，默认为生成新的数据框而非就地操作。
<!--ID: 1705567264256-->
END