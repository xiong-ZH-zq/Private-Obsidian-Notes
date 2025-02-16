---
type: math_note
date_creation: 2024-02-20
related_book:
---
# NKU实变函数第一课

## Intro
- 实变函数主要研究课题：Lebesgue 积分
- 解决的主要问题：运算符换序的问题. 在数学分析当中，广义积分的运算符换序问题较为复杂.
例如，对于广义积分的如下问题：
$$
\int_a^{+\infty}\mathrm{d}x\int_c^\infty f(x,y)\mathrm{d}y = \int_c^\infty \mathrm{d}y\int_a ^\infty f(x,y)\mathrm{d}x
$$
等式成立需要什么条件？在 Riemann 积分的背景下这个问题相对比较困难，因此在实变函数当中引入 Lebesgue 积分.

回顾 Riemann 积分：
$$
\lim_{\max(x_k-x_{k-1})\to 0} \sum\limits_{k=1}^n f(\xi_k)(x_k-x_{k-1})
$$
**存在有限** 时（注意，在实变函数当中，极限趋于无穷我们也说*存在* ）就是 Riemann 积分的值，否则 Riemann 不可积.

而 Lebesgue 积分相当于“横着切”，写为如下的表达式：
$$
\sum\limits_{k=1}^n |\left\lbrace x: y_{k-1}\leqslant f(x)< y_k \right\rbrace| y_{k-1}
$$
在此仅作一个感觉上的介绍，在后续会有更深入的讨论.

## 集合
该部分冗余部分较多，参考[[集合、映射与关系]]进行复习即可.
### 集族
设 $X$ 是集合，由 $X$ 的某些子集构成的集合称为 **集族** ，设 $\mathcal{X}$ 为 $X$ 上的集族，那么 $\mathcal{X}$ 中所有集合的并称为 $\mathcal{X}$ 的并，即为：
$$
\bigcup \left\lbrace A: A\in \mathcal{X} \right\rbrace = \left\lbrace x: \exists A\in X, \text{s.t. } x\in A\right\rbrace
$$
集族的交基本类似，不做赘述.

## 集合序列的极限
### 集合序列的单调性
设集合序列 $\left\lbrace A_n \right\rbrace_{n\geqslant1}$ ，那么称若
$$
A_1\subset A_2 \subset \cdots \subset A_n\subset \cdots
$$
则该集合序列单调增，反向则为单调减.

### 集合序列的上下极限
现在任意给定一个集合序列 $\left\lbrace A_n \right\rbrace_{n\geqslant 1}$ ，构造两个集合序列为
$$
B_n = \bigcup_{k=n}^\infty A_k  , C_n = \bigcap_{k=n}^\infty A_k
$$
根据单调性的定义，我们不难判断 $\left\lbrace B_n \right\rbrace$ 是单调减的，而 $\left\lbrace C_n \right\rbrace$ 是单调增的，此时我们就有集合序列的上下极限的定义：
>[!note] 定义：集合序列的上极限和下极限
> 我们把 $\left\lbrace B_n \right\rbrace$ 的交称为 $\left\lbrace A_n \right\rbrace$ 的上极限，记为：
>  $$ \varlimsup_{n\to \infty} A_n  =  \bigcap_{n=1}^\infty \bigcup_{k=n}^\infty A_k $$
>  相应的，下极限为 $\left\lbrace C_n \right\rbrace$ 的并，记为：
>  $$ \varliminf_{n\to \infty} A_n  =  \bigcup_{n=1}^\infty \bigcap_{k=n}^\infty A_k $$

我们该如何理解这个概念？对于 $B_n$ ，可以理解为 $n$ 趋近无穷的过程是不断去掉 $A_n$ 的一个过程，因此最终的**上极限就是无穷多个** $A_k$ **都包含的集合**，里面的元素存在于无穷多个 $A_k$ 当中.

反之对于下极限也是一样，有限多个 $A_k$ 不含有的元素构成了下极限，这个在后续会进行讨论.

>[!faq] 例题
>考虑集合 $A_n = \left\lbrace \dfrac{m}{n} : m\in \mathbb{Z} \right\rbrace$ ，证明： $\displaystyle\varlimsup_{n\to \infty}{A_n} = \mathbb{Q}$ ， $\displaystyle\varliminf_{n\to \infty}{A_n} = \mathbb{Z}$ .

首先 $\mathbb{Z}\subset A_n \subset \mathbb{Q}$ 可知
$$
\mathbb{Z} \subset \varliminf_{n\to \infty}{A_n} , \varlimsup_{n\to \infty}{A_n} \subset \mathbb{Q}
$$
先证明 $\displaystyle\varliminf_{n\to \infty}{A_n} \subset \mathbb{Z}$  ，此时考虑设 $\displaystyle x\in \varliminf_{n\to \infty}{A_n}$ ，存在 $n$ 使得 $x\in A_n\cap A_{n+1}$ （实际上也就是存在 $n_0$ 使得 $x\in \displaystyle\bigcap_{k=n_0}^\infty A_k$ ），此时我们有
$$
x = \frac{m_{n}}{n} = \frac{m_{n+1}}{n+1}
$$
其中 $m_n$ 和 $m_{n+1}$ 是整数，那么根据差比性质有 $x = m_{n+1}-m_n\in \mathbb{Z}$ ，从而包含关系成立.

再证明 $\mathbb{Q} \subset \displaystyle\varlimsup_{n\to \infty}{A_n}$ ，设 $x\in \mathbb{Q}$ ，此时有 $x = \dfrac{p}{q}, p,q\in \mathbb{Z}$ . 那么对于**任何** $n$ ，总有 
$$
\dfrac{p}{q} = \dfrac{np}{nq} \in \displaystyle\bigcup_{k=n}^\infty A_k
$$ 
进而可以证明包含关系成立，从而题中结论成立. $\square$



