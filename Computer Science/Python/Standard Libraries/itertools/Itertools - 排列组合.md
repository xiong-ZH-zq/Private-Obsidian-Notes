---
type: Code_Card
date_creation: 2024-01-30
code_language: python
---

TARGET DECK: Code::python::itertools

START
Programming
请查看如下的表格，输入无序有放回的 Python 函数 (Itertools)，从字符串 `'ABCD'` 产生，抽取次数为 $3$ 次.

| 顺序与抽样方式 | 有序 | 无序 |
| :--: | :--: | :--: |
| **有放回** | $n^r$ | $\displaystyle\binom{n+r-1}{r}$ |
| **无放回** | $\dfrac{n!}{r!}$ | $\displaystyle\binom{n}{r}$ |
Back: 
```python
combinations_with_replacement('ABCD',3)
```
Addition: 
返回的结果为 Itertools 专用对象，一般而言可以直接遍历.
[[Itertools - 排列组合]]
<!--ID: 1706670238458-->
END