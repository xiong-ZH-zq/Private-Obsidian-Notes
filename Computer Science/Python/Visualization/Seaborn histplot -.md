---
type: Code_Card
date_creation: 2024-02-08
code_language: python
---

TARGET DECK: Code::python::visualization

START
Programming
现有 `data` 为 numpy 数组，请使用 Seaborn （简化为 `sns` ）直接绘制为条形图，并通过核密度估计平滑出相应的曲线，结果如下所示：
![[Seaborn histplot --20240208.png]]
Back: 
```
sns.histplot(data,kde=True)
```
Addition: 
`kde` 参数即为核密度估计，使用 `kde` 后图像中即会出现平滑曲线.
<!--ID: 1707395819668-->
END