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

>[!example] 语义模型的一些性质
>1. 对于任意的 $\psi$ ，$\mid\!\equiv\psi \iff \varnothing \mid\!\equiv \psi$ .
>2. 对于任意的 $\varphi_0,\cdots,\varphi_n,\psi$ ，以下等价：
>	1. $\left\lbrace \varphi_0,\cdots,\varphi_n \right\rbrace \mid\!\equiv \psi$ ；
>	2. $\varphi_0 \land \cdots \land \varphi_n \mid\!\equiv \psi$ ；
>	3. 对于任意 $i<n$ ，$\left\lbrace \varphi_0,\cdots,\varphi_{i-1} \right\rbrace \mid\!\equiv \varphi_i \land \cdots \land \varphi_n \to \psi$

上述性质由定义可以直接导出. $\square$

>[!examples] 集合与模型的关系
>对于任意的集合 $\Gamma$ 和 $\Delta$ ，以及任意的语句 $\varphi$ 和 $\psi$ ，
>
> 1. $\Gamma \subseteq \Delta \Rightarrow \mathrm{Mod}(\Delta) \subseteq \mathrm{Mod}(\Gamma)$ .
> 2. $\Gamma \mid\!\equiv \psi$ 当且仅当 $\mathrm{Mod}(\Gamma) \subseteq \mathrm{Mod}(\psi)$ .
> 3. 若 $\Gamma \subseteq \Delta$ 且 $\Gamma \mid\!\equiv \psi$ ，那么 $\Delta \mid\!\equiv \psi$ ;
> 4. $\Gamma \cup \left\lbrace \varphi \right\rbrace \mid\!\equiv \psi\iff \Gamma \mid\!\equiv \varphi \to \psi$.

对其中的第四条作一个解释（看着比较抽象）.
当 $\Gamma \cup \left\lbrace \varphi \right\rbrace \mid\!\equiv \psi$ 为真时，说明集合 $\Gamma\cup \left\lbrace \varphi \right\rbrace$ 的任意一个模型 $V$ 都有 $V(\psi) = \mathrm{T}$ . 
根据蕴涵的关系，仅需考虑 $\Gamma \mid\!\equiv \varphi$ 为真的情形，也就是说对于 $\Gamma$ 的任意真值指派 $V$，$V(\varphi)=\mathrm{T}$ ，这也就说明 $V$ 是 $\Gamma\cup \left\lbrace \varphi \right\rbrace$ 的模型，从而 $V(\psi)=\mathrm{T}$ . 故右侧命题成立.

右侧到左侧也是类似的.




## 命题理论的概念
### 命题理论的定义与定理
我们再看 $\Gamma \mid\!\equiv \psi$ ，它可以看作一个说法的符号表示：“在 $\Gamma$ 的假定（公理）下可以推导出 $\psi$”. 因此，有命题理论的定义：

>[!note] 定义：命题理论
>若一个语句集合 $T$ 在语义后承的意义下封闭，那么则称 $T$ 为一个**命题理论** (Propositional Theory)，也就是说，对于命题理论 $T$ 中任意的 $\varphi$ ,恒有
> $$ T \mid\!\equiv \varphi \Rightarrow \varphi\in T. $$
> $T$ 中的元素也被称为**定理** (Theorem).

>[!note] 定义：生成的理论，公理
>对于任意语句集 $\Gamma$ ，由 $\Gamma$ **生成**的命题理论为集合：
>$$ \mathrm{Th}(\Gamma) = \left\lbrace \psi: \Gamma \mid\!\equiv \psi \right\rbrace .$$
>我们称 $\Gamma$ 是 $\mathrm{Th}(\Gamma)$ 的**公理**集合.

结合前面的性质，可以导出如下简单结论：
- $\Gamma \subseteq \mathrm{Th(\Gamma)}$;
- $\mathrm{Mod}(\Gamma) = \mathrm{Mod}(\mathrm{Th}(\Gamma))$ ;
- $\mathrm{Th}(\Gamma)$ 是一个命题理论；
- $\Gamma \subseteq \Delta \Rightarrow \mathrm{Th}(\Gamma)\subseteq \mathrm{Th}(\Delta)$ ;
- $\Gamma$ 是一个命题理论当且仅当 $\Gamma= \mathrm{Th}(\Gamma)$ ;
- $\mathrm{Th}(\Gamma)$ 是具有性质 $\Gamma \subseteq T$ 的集合 $T$ ;
- $\mathrm{Th}(\varnothing) = \left\lbrace \varphi: \varphi \text{ is a tautology} \right\rbrace$ 被包含在所有的命题理论当中.


## 命题理论的相容
### 语句集的相容

>[!note] 定义：语句集的相容和完全
>对于任意语句集 $\Gamma$ ，
>
>(i) 若 $\Gamma$ 至少有一个模型，则 $\Gamma$ 是**相容** (consistent) 的，否则则称**不相容** (inconsistent).
>
>(ii) 若对于任何语句 $\varphi$ ， $\varphi\in\Gamma$ 和 $\neg\varphi\in \Gamma$ 总有且仅有一个属于 $\Gamma$ ，则称 $\Gamma$ 为**完全** (Complete) 的. 否则则为**不完全** (Incomplete) 的.

### 真值指派的理论

>[!note] 定义：真值指派的理论
>对于任意的真值指派 $V$ ，$V$ 的**理论**定义为集合：
>$$ \mathrm{Th}(V) = \left\lbrace \psi: V(\psi)=\mathrm{T} \right\rbrace $$
>


>[!note] 定理
>对于任何的真值指派 $V$ ，
>
>(i) $\mathrm{Th}(V)$ 是一个完全且相容的命题理论，并且 $V$ 是其唯一的模型.
>
>(ii) 对于任意的真值指派 $W$ ，$V=W\iff \mathrm{Th}(V) = \mathrm{Th}(W)$ .

$\mathrm{Th}(V)$ 有 $V$ 这一个模型，从而相容，并且对于 $\varphi\in \mathrm{Th}(V)$ ，$V(\varphi) = \mathrm{T} \iff V(\neg\varphi) = \mathrm{F}$ ，因此它也是完全的.
最后，如果存在另一个模型 $W$ ，那么 $V(\varphi)=\mathrm{T}$ 成立时，自然有 $W(\varphi) = \mathrm{T}$ 成立，反过来：
$$
V(\varphi)=\mathrm{F} \Rightarrow V(\neg \varphi)=\mathrm{T}\Rightarrow W(\neg \varphi) = \mathrm{T} \Rightarrow W(\varphi) =\mathrm{F}
$$

从而 $V=W$ 成立. $\square$


### 命题理论集合的势

>[!note] 定理：命题理论不可数
>对于集合 $E =\left\lbrace T: T \text{ is a propositional theory} \right\rbrace$ ，也就是所有命题理论构成的集合，它的势是多少？

一方面，由推论可知集合 $E$ 至少为连续统势，另一方面，$T \subseteq \mathrm{Sent}_L$ ，因此 $E \subseteq \mathcal{P}(\mathrm{Sent}_L)$ ，其中 $\mathcal{P}(A)$ 表示 $A$ 的幂集. 那么由于 $\mathrm{Sent}_L$ 是可数集，则 $E$ 的势不超过连续统势，合起来可知 $E$ 的势是连续统势. $\square$

### 


## 命题理论集合的结构



## 紧性 (Compactness)
### PCT 与有限相容

### APCT