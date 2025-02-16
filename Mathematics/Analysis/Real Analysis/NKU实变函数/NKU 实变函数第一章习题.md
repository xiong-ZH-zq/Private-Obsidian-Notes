---
type: math_note
date_creation: 2024-02-25
related_book:
  - "[[实变函数 - 孙文昌]]"
---
# NKU 实变函数第一章习题
## 符号约定

| 书本符号/术语         | 笔记符号/术语              |
| --------------- | -------------------- |
| $\mathbf{Q}$    | $\mathbb{Q}$         |
| $\bar{\bar{A}}$ | $\textbar A\textbar$ |
| 完全一一映射          | 双射                   |
| 一一映射            | 单射                   |
| $a$             | 有理数集的基数              |
| $c$             | 连续统势                 |

## 基本的集合运算
### 对称差

对于对称差，以下的计算性质需要记住：
1. $A \Delta A = \varnothing$ .
2. $A \Delta \varnothing = A$ .
3. 结合律（第一章 T4(ii)）


>[!faq] 第一章 T4(i)
>对任何集合 $A$ 和 $B$ ，必有集合 $C$ 使得 $A \Delta C = B$.

直接考虑先变为空集： $A \Delta A$ ，然后直接取 $B$ 即可：
$$
A \Delta A \Delta B = B
$$
$\square$

## 证明具体集合为可数集
### 构造可数集合
>[!faq] 第一章T8
> 设 $f$ 是 $\mathbb{R}$ 上的实函数，若有 $M>0$ ，使对任何有限个两两不等的实数 $x_1,x_2,\cdots,x_n$ 都有：
> $$\left|\sum\limits_{i=1}^n f(x_i)\right|\leqslant M$$
> 求证：$\left\lbrace x: f(x)\neq 0 \right\rbrace$ 是至多可数集.

首先，为证明这个集合为可数集，我们需要**将其转化为更好分解的形式**：
$$
\left\lbrace x: f(x)\neq 0 \right\rbrace = \left\lbrace x: f(x)>0 \right\rbrace \cup \left\lbrace x: f(x)<0 \right\rbrace
$$
我们仅需考虑 $\left\lbrace x: f(x)>0 \right\rbrace$ 的部分，考虑直接进行如下的构造：
$$
\left\lbrace x: f(x)>0 \right\rbrace  = \bigcup_{i=1}^\infty \left\lbrace x: f(x)> \frac{1}{n} \right\rbrace
$$
对于每个单独的 $\left\lbrace \displaystyle x: f(x)> \frac{1}{n} \right\rbrace$ ，它都是有限集，如果不然，那么可以从中取出 $nM$ 个点使得
$$
\sum\limits_{i=1}^{nM} f(x_i) > M
$$
出现矛盾，因此上述的集合都是有限集，这就说明原集合是可数个有限集的并，从而为至多可数集. $\square$

### 构造可数集的并
>[!faq] 第一章T18
>求证：有限 $n$ 元数列全体及有理系数多项式全体都是可数集.

有限 $n$ 元数列设有 $m$ 项，则可以给定双射：
$$
\begin{aligned}
&f: \left\lbrace a_1, a_2,\cdots , a_m \right\rbrace
= 
\\
&(m,a_1,a_2,\cdots,a_m)\in \mathbb{N}\times \left\lbrace 0,1,\cdots,n-1 \right\rbrace\times \cdots \left\lbrace 0,1,\cdots,n-1 \right\rbrace
\end{aligned}
$$
这是 $\mathbb{N}$ 与可数个有限集的直积，自然是可数的，从而从 $m=1$ 并到 $\infty$ 即可. 多项式全体也是类似的. $\square$

>[!warning]- 注意
>注意不要弄混了并和直积的可数性关系.

### 构造集合直积/并
>[!faq] 第一章 T18(ii)
>证明：有理系数多项式全体构成的集合为可数集.

>[!danger]+ 易错做法
> 这个题目有个非常易错的做法是将以下的多项式直接映射：
>  $$ f: a_0+a_1x+a_2 x^2 +\cdots + a_n x^n + \cdots \to (a_0,a_1,\cdots,a_n,\cdots)$$
>  其中右侧是一个数列，这样似乎构造了一个映射，但是可以发现它将会证明出题中集合是具有连续统势的. 这就出现了非常尴尬的情况. 事实上，这是由于映射到的集合中还包含了幂级数（多项式一定是有限的），从而映射就不再是满射.







## 具体双射构造
### Hilbert 旅馆与区间之间的双射
>[!faq] 第一章 T22(i)
>具体构造下列集合之间的一个双射：
>
>(i) $[0,1]$ 和 $(0,1)$

下面我们来回顾一下 Hilbert 旅馆的思想：
- 当一个客人来到已经住满了的无限旅馆，只需要让每个客人都挪动到后一个房间；
- 无限个客人来到时，只需要每个客人都挪动到自己房间号两倍的对应房间.
我们现在来看这个问题，就能发现这类问题的一个通用解法：找到对应的**来客**，并且找到适当的**挪动策略**即可。

解：
我们发现 $0,1$ 是有限的两个**来客**，此时只需要找到对应的挪动策略。设映射为 $f$ ，那么我们首先设 “旅馆” 为
$$
A = \left\lbrace 0,1,\frac{1}{2},\frac{1}{3},\cdots , \frac{1}{n},\cdots \right\rbrace
$$
对 $x\not\in A$ ，统一 $f(x) = x$ ，而对于 $x\in A$ ，我们只需让每个客人往后挪动两位即可：
$$
f\left(x\right) = 
\begin{cases} \dfrac{1}{2} ,x=0\\
\dfrac{1}{\frac{1}{x}+2}, x \in \mathbb{N}_+ \\
\end{cases}
$$
此时我们构造的双射 $f$ 已经满足题意. $\square$

>[!hint] HINT
>事实上这个方法已经是构造区间之间双射的通法，只需要找到“来客”和移动策略即可.

>[!faq] 拓展
> 现在将条件限制：我们能否构造出一个对应的**连续**双射？

### 不可数集及其直积间的双射
这个部分主要是**对角线方法**和**小数表示**的应用.

>[!faq] 第一章 T22(ii)
>具体构造下列集合之间的一个双射：
>
>(ii) $(0,1]$ 与 $(0,1]\times (0,1]$

这两个集合显然都具有连续统势，在 [[集合的等价、基数#连续统势]] 一节当中，我们对于直积的处理是使用对角线方法.

对于 $(0,1]$ ，我们首先利用小数表示将其与二元数列全体进行一一对应，也就是：
$$
\begin{aligned}
&x = \sum\limits_{i=1}^\infty \frac{x_i}{2^i}, \\
&f(x) = (x_1,x_2,\cdots,x_n,\cdots)
\end{aligned}
$$
$f$ 显然为双射.

然后我们再将 $(0,1]\times (0,1]$ 作一一对应：
$$
\begin{aligned}
x_1^{(1)},x_2^{(1)},\cdots \\
x_1^{(2)},x_2^{(2)},\cdots
\end{aligned}
$$
这里直接按照每列数，对于一个 $(x_1,x_2)\in (0,1]\times (0,1]$ ，都有
$$
 g: (x_1,x_2) \to (x_1^{(1)},x_1^{(2)},x_2^{(1)},\cdots)
$$
因此构造出了一个到二元数列的双射，因此将两个映射复合有 $fg^{-1}$ 为两个集合间的完全一一映射. $\square$

## 集合基数的比较
### 利用 Bernstein 定理
>[!faq] 第一章习题 T23
>求证：$\mathbb{R}$ 上的实函数全体有基数 $2^c$ .

>[!hint]- HINT
>在连续统势或者超越连续统势的集合基数出现的情况下，考虑 Bernstein 定理会相对较为简单.

考虑利用 Bernstein 定理，设 $\mathbb{R}$ 上的实函数全体为 $\mathcal{F}$ .

首先证明 $|\mathcal{F}|\geqslant 2^c$ ，考虑**特征函数** $\chi_A$ ，其中 $A\subset \mathbb{R}$ ，从而对于 $\mathbb{R}$ 的任何子集都有 $\mathcal{F}$ 中的 $\chi_A$ 与其对应.

反过来证明 $|\mathcal{F}| \leqslant 2^c$ ，考虑**函数的点集合**：
$$
\left\lbrace (x,f(x)): x\in A, A\subset \mathbb{R} \right\rbrace
$$
从而对于任意 $f\in \mathcal{F}$ ，都有 $\mathbb{R}^2$ 的子集与之对应，由于 $\mathbb{R}\sim \mathbb{R}^2$ ，从而得证. $\square$

