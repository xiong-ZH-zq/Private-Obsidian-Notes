---
type: math_note
date_creation: 2024-03-01
related_course:
  - "[[计算机集合论与逻辑 - 李军]]"
---
# 归纳与递归(Induction and Recursion)
## 归纳系统 (induction system)
在学完数学归纳法和语句归纳法后，实际上我们可以考虑抽象出归纳的概念.

对于每个自然数 $n$ ，都有一个性质 $\mathcal{P}$ ，可以记为 $\mathcal{P}(n)$ ，**归纳假设**实际上就是对于一个固定的 $n$ ，$\mathcal{P}(n)$ 成立时，可以推导出 $\mathcal{P}(n+1)$ .

此时我们记
$$
Y_{\mathcal{P}} = \left\lbrace n \in \omega : \mathcal{P}(n) \right\rbrace
$$
（注意 $\omega$ 为自然数集）
归纳步骤实质上就是证明 $Y_{\mathcal{P}}$ 是**封闭**的. 最终的结论就是 $Y_{\mathcal{P}}=\omega$ .

对于语句归纳法，原子语句情形就是**广义的** $0$ 的情形，而**后继函数**也类似，考虑利用集合的语言来进行概括.

>[!note] 定义：归纳系统 (Induction System)
>一个**归纳系统**就是一个三元组 $\mathcal{X}=(X,X_0,\mathcal{H})$ ，其中 $X$ 为非空集合，$X_0 \subset X$ 且 $\mathcal{H}$ 为 $X$ 上的**有限函数**集合.
>
