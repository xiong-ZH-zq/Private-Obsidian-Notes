---
type: math_note
date_creation: 2024-03-07
related_book:
  - "[[📕李贤平概率论]]"
---
# 条件概率、全概率公式、Bayes 公式
## 条件概率
### 条件概率的定义
>[!note] 定义：条件概率
>设 $(\varOmega,\mathscr{F},P)$ 是一个概率空间，$B\in \mathscr{F}$ ，而且 $P(B)>0$ ，则对任意 $A\in \mathscr{F}$ ，记
>$$ P(A\mid B) = \frac{P(AB)}{P(B)}$$
>并称 $P(A\mid B)$ 为在事件 $B$ 发生的条件下，事件 $A$ 发生的**条件概率**.

这里的 $P(B)>0$ 是讨论的一个前提，若 $P(B)=0$ ，这个时候 $P(AB)=0$ 也是必然的，这就出现了 $\frac{0}{0}$ 的未定型，现在这个问题暂时超出了目前的范围，在以后的科目学习中会进一步学到.

乘开之后，就能得到概率的乘法公式：
$$
P(AB) = P(B)P(A|B)
$$
条件概率也满足概率公理的三个条件（非负性、规范性，可列可加性）

### 条件概率的性质
由于其满足概率公理，可以导出一些本来已知的一些性质：

- $P(\varnothing \mid B)=0$ ；
- $P(A_1\cup A_2 \mid B) = P(A_1\mid B)+P(A_2\mid B)-P(A_1A_2\mid B)$ .


推广的乘法公式：
$$
P(A_1A_2\cdots A_n) = P(A_1)P(A_2\mid A_1) \cdots P(A_n| A_1A_2 \cdots A_n)
$$
## 全概率公式