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

条件概率实际上是对样本空间的一个限制，如果将 $B$ 设为 $\varOmega$ ，那这就是我们学过的概率.


### 条件概率的性质
由于其满足概率公理，可以导出一些本来已知的一些性质：

- $P(\varnothing \mid B)=0$ ；
- $P(A_1\cup A_2 \mid B) = P(A_1\mid B)+P(A_2\mid B)-P(A_1A_2\mid B)$ .


推广的乘法公式：
$$
P(A_1A_2\cdots A_n) = P(A_1)P(A_2\mid A_1) \cdots P(A_n| A_1A_2 \cdots A_n)
$$
>[!faq] 例题：Polyá 坛子模型
>坛子中有 $b$ 个黑球和 $r$ 个红球，随机取出一个，把原球放回，并加进与抽出的球同色的球 $c$ 只，再摸第二次，这样下去总共摸了 $n$ 次，问前面的 $n_1$ 次取出黑球，后面的 $n_2=n-n_1$ 次出现红球的概率是多少？

以 $A_1$ 表示第一次摸出黑球这一个事件，$\cdots$ ，$A_{n_1}$ 表示第 $n_1$ 次摸出黑球，$A_{n_1+1}$ 表示第 $n_1+1$ 次摸出红球，$\cdots$ ， $A_n$ 表示第 $n$ 次摸出红球.

由于条件概率更好计算，使用推广乘法公式是较为简单的，对于前 $n_1$ 次，可以计算得到：
$$
P(A_{n_1} \mid A_1\cdots A_{n_1-1}) = \dfrac{b+(n_1-1)c}{b+r+(n_1-1)c}
$$
计算到 $n$ 次也是一样的：
$$
P(A_n \mid A_1\cdots A_{n-1})=\dfrac{r+(n_2-1)c}{b+r+(n-1)c}
$$
从而

$$
P(A_1A_2\cdots A_n) = \prod_{i=0}^{n_1-1}\frac{b+ic}{b+r+ic}\prod_{j=0}^{n_2-1}\frac{r+jc}{b+r+(n_1+j)c}
$$
$\square$
## 全概率公式
### 全概率公式的定义
>[!note] 定义：完备事件组
>设事件 $A_1,A_2,\cdots,A_n,\cdots$ 是样本空间的一个**分割**，亦称**完备事件组**，即 $A_i(i=1,2,\cdots,n,\cdots)$ 两两不相容，而且
>$$ \sum\limits_{i=1}^\infty A_i = \varOmega $$

对于完备事件组，考虑事件 $B$ ：
$$
B = \sum\limits_{i=1}^\infty A_iB
$$
从而根据可列可加性，有
$$
P(B) = \sum\limits_{i=1}^\infty P(A_i B)
$$
再利用乘法公式可以得到全概率公式：

>[!note] 定理：全概率公式
> $$ P(B) = \sum\limits_{i=1}^\infty P(A_i)P(B\mid A_i) $$


### 全概率公式的应用

从 Polyá 坛子模型当中抽象出一个更一般的摸球模型：

> 坛子中有 $b$ 个黑球和 $r$ 个红球，随机取出一个，并加进与抽出的球同色的球 $s$ 只，再摸第二次，这样下去总共摸了 $n$ 次，求证：第 $n$ 次摸出红球的概率为 $\dfrac{r}{b+r}$ .

设 $R_n$ 为第 $n$ 次摸出红球的事件，那么考虑利用数学归纳法.

对于 $n=1$ 时的情形，显然成立，随后对 $n-1$ 的情形成立时，考虑对 $n$ 的情形.

此时，考虑全概率公式：
$$
P(R_n) = P(R_1)P(R_n \mid R_1) + P(\overline{R_1})P(R_n \mid \overline{R_1})
$$
这里面，实际上就是 $P(R_n \mid R_1)$ 概率需要求，此时有如下的想法：此时的 $R_1$ 已发生，那么 $R_n$ 的发生等价于在 $b+r+s-1$ 个球里面，第 $n-1$ 次抽出 $r+s-1$ 个红球中的一个，从而就能利用归纳假设了.
$$
\frac{r}{b+r}\dfrac{r+s-1}{b+r+s-1}+\frac{b}{b+r}\frac{r}{b+r+s-1}
= \frac{r}{b+r}
$$
$\square$


## Bayes 公式
考虑
$$
B = \sum\limits_{i=1}^\infty BA_i
$$
此时由于
$$
P(A_i B) = P(A_i)P(B\mid A_i)
$$
可以推得
$$
P(A_i \mid B) = \frac{P(A_i)P(B\mid A_i)}{P(B)}
$$
从而利用全概率公式可以得到

>[!note] 定理：Bayes 公式
>$$P(A_i\mid B) = \dfrac{P(A_i)P(B\mid A_i)}{\sum\limits_{i=1}^\infty P(A_i)P(B\mid A_i)}$$

