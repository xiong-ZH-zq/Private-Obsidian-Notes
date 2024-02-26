---
type: math_note
date_creation: 2024-02-25
related_book:
  - "[[实变函数 - 孙文昌]]"
---
# NKU 实变函数第一周作业
## 证明具体集合为可数集
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

## 具体双射构造
### Hilbert 旅馆与区间双射
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
f(x) = 
\begin{cases} \dfrac{1}{2} ,x=0\\
\dfrac{1}{x+2}, x \in \mathbb{N}_+ \\
\end{cases}
$$
此时我们构造的 $f$ 已经满足题意. $\square$

>[!hint] HINT
>事实上这个方法已经是构造区间之间双射的通法，只需要找到“来客”和移动策略即可.

>[!faq] 拓展
> 现在将条件限制：我们能否构造出一个对应的**连续**双射？

