---
type: math_note
date_creation: 2024-03-06
related_course:
  - "[[计算机集合论与逻辑 - 李军]]"
---
# 命题理论(Propositional Theories)

## 语句集 $\Gamma$ 的模型、$\Gamma$ 的语义后承概念
### 语句集 $\Gamma$ 的模型

>[!note] 定义：语句集 $\Gamma$ 的模型
>对于任意语句集合 $\Gamma$，
>
> 1. 一个真值指派 $V$ 是 $\Gamma$ 的**模型**当且仅当对于所有的 $\varphi\in \Gamma$ 都有 $V(\varphi) = \mathrm{T}$  ； $\mathrm{Mod}(\Gamma)$ 是 $\Gamma$ 的所有模型组成的集合.
> 2. 对于任意的语句 $\psi$ ，$\Gamma \mid\!\equiv \psi$ 当且仅当对于 $\Gamma$ 的所有模型 $V$ ，都有 $V(\psi)= \mathrm{T}$ .

如果 $\psi\in \Gamma$ ，那么 $\Gamma \mid\!\equiv \psi$ .

>[!faq] 例题
>请求出 $\Gamma = \left\lbrace p_{n+1}\to p_n : n\in \omega \right\rbrace$ 所有的模型，也就是 $\mathrm{Mod}(\Gamma)$ .

首先，对于 $\forall n \in \omega$ 都能有 $V(p_n) = \mathrm{T}$ 的所有真值指派 $V$ 自然都是 $\Gamma$ 的模型.

对于剩下的情形，都要满足 $V(p_{n+1}\to p_n) = \mathrm{T}$ ， 此时真值指派需要满足对于某个 $n$ 有
$$
V(p_i) = 
\begin{cases}
\mathrm{T} , i \leqslant n \\
\mathrm{F} , i > n .
\end{cases}
$$
因此我们列举了所有的可能模型. $\square$

>[!note] 语义模型的一些性质
>


## 命题理论的概念