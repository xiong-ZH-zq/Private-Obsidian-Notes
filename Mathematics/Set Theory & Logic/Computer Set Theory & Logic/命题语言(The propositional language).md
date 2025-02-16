---
type: math_note
date_creation: 2024-02-28
related_course:
  - "[[计算机集合论与逻辑 - 李军]]"
---

# 命题语言(The Propositional Language)
## 集合计算与字符串表达式
我们在计算机集合论与逻辑中沿用我们以前曾学到的集合计算（交并补差、直积），因此不多做赘述.

对于可数个可数集 $X$ 的直积，我们约定符号 $X^{<\omega}$ 为可数个集合的直积. 如果我们在 $X$ 当中拥有的元素是字符，那么此时直积后得到的集合将会是**全体字符串的集合**. 

## $L$ 表达式与 $L$ 语句
### 符号集和表达式集
在有字符串的表示概念后，我们定义符号集为 $\mathrm{Symb}$ ，其中包含了字符.

所有的表达式都是 $\mathrm{Symb}$ 中字符的组合（直积），表达式集合因而可以写为：
$$
\mathrm{Expr} = \mathrm{Symb}^{< \omega}
$$
对于某个已经确定的语言，我们可以用下标来标识，例如设 $E$ 为英语，就有
$$
\mathrm{Symb}_E = \left\lbrace a,b,c,\cdots,x,y,z \right\rbrace
$$
### $L$ 表达式
现在我们将语言固定为**命题语言**，用 $L$ 表示，其符号集为
$$
\mathrm{Symb}_L = \left\lbrace p_0,p_1,\cdots \right\rbrace \cup \left\lbrace \neg , \lor,\land, \to, \leftrightarrow \right\rbrace
$$
其中 $\neg$ 为**非**，$\lor$ 为**或**，$\land$ 为**且**，$\to$ 为**推导**(implies)，$\leftrightarrow$ 为**当且仅当**(If and only if). 这 $5$ 种符号称为**连接词**，而 $p_i$ 称为**语句符号**(sentence symbol).

这 $5$ 个连接词也可说明为：否定、合取、析取、蕴涵和双向蕴涵.


$L$-表达式实质上就是 $\mathrm{Expr}_L$ 的元素，例如以下的表达式就是一个 $L$-表达式：
$$
\neg (p_1 \lor p_2)\land p_3
$$
此外还有 $L$-原子表达式的定义：

>[!note] 定义：$L$-原子表达式 ($L$-atomic sentence)
> $L$-原子表达式是仅包含一个**语句符号**的 $L$-表达式.

也就是说 $p_0,p_1,\cdots$ 为 $L$-原子表达式.

### 前缀表达式
前缀表达式是一种表达式的表示方式，它规避了中缀表达式（也就是我们常用的表达式）需要括号的缺点.

>[!hint] 前缀表达式
>前缀表达式在后续的内容当中基本出现在命题的证明当中，必须掌握它的读写，但是在自己书写的时候还是别虐待自己用前缀表达式写作业了 (doge).

下面给出了一个前缀表达式的组成结构：
![[命题语言(The propositional language)-20240228.png|600]]
根据图像，前缀表达式
$$
\lor \neg p_2 \land p_4 \neg p_1
$$
转化为中缀表达式之后为：
$$
\neg p_2 \lor (p_4 \land (\neg p_1))
$$
这个部分找一些例子试着自己倒弄一下就行.

### $L$-语句 ($L$-Sentence)
下面给出 $L$-语句的定义：

>[!note] 定义：$L$-语句
>定义 $\mathrm{Sent}_n$ 为全体 $n$ 阶 $L$-语句集合，那么有如下定义：
>
>1. $\mathrm{Sent}_0$ 为全体 $L$-原子表达式 的集合；
>2. $\mathrm{Sent}_{n+1} := \mathrm{Set}_{n}\cup \left\lbrace \neg \varphi : \varphi\in \mathrm{Sent}_n  \right\rbrace\cup \left\lbrace \bullet \varphi \psi : \varphi, \psi\in \mathrm{Sent}_n \right\rbrace$  其中 $\bullet$ 为二元逻辑连接词；
>3. $\mathrm{Sent}_L := \displaystyle\bigcup_{n\in \omega}\mathrm{Sent}_n$ .
>
> $\mathrm{Sent}_L$ 中的元素，称为 $L$-**语句**.

对于 $L$-语句 $\varphi$ ，如果
$$
\varphi\in \mathrm{Sent}_n ,\varphi\not\in \mathrm{Sent}_{n-1}
$$
就称 $\varphi$ 为 $n$ 阶 $L$-语句.

>[!note] 引理：$\mathrm{Sent}_L$ 为最小集合
>$\mathrm{Sent}_L$ 是包含 $\mathrm{Sent}_0$ 且在 $5$ 个连接词的意义下封闭 (closed) 的最小集合.

包含不需要证明，运算封闭性：对于 $m$ 阶语句 $\varphi$ 和 $n$ 阶语句 $\psi$ ，取 $p = \max(m,n)$ ，它们自然属于 $\mathrm{Sent}_p$ ，同时加上一个逻辑连接词后自然属于 $\mathrm{Sent}_{p+1}$ . 从而封闭性成立.

对于具有上述两个性质的集合 $\Gamma$ ，不难证明对于任意的 $n$ 均有 $\mathrm{Sent}_{n} \subseteq \Gamma$ ，从而 $\mathrm{Sent}_L \subseteq \Gamma$ . $\square$

## 语句归纳法与数学归纳法
下面引入语句归纳法，正是由于 $\mathrm{Sent}_L$ 本身的封闭性以及它是具有这种性质的最小集合，我们才能有语句归纳法这样的方法.

数学归纳法可以简单概括为，如果在 $n=1$ 的情况下，命题 $\mathcal{P}$ 成立，在 $n$ 的情形成立 $\mathcal{P}$ 时，$n+1$ 的情形也将成立 $\mathcal{P}$ ，从而完成 $\mathcal{P}$ 的证明.

对于语句，由于连接词仅有有限的几个，它也能进行逻辑上的归纳.

下面给出语句归纳法的步骤：
>[!note] 定理：语句归纳法
>对于一个针对 $L$-表达式的性质 $\mathcal{P}$ ，如果：
> 1.  (归纳基础) 每个 $L$-原子语句都具有性质 $\mathcal{P}$ ；
> 2.  (归纳步骤) 如果 $\varphi$ 和 $\psi$ 都具有性质 $\mathcal{P}$ ，那么 $\neg \varphi$ 和 $\varphi\bullet \psi$ 都具有性质 $\mathcal{P}$ （其中 $\bullet$ 为二元连接词）；
> 
> 那么此时就能证明所有的 $L$-表达式都具有性质 $\mathcal{P}$ .

设 $\Gamma$ 是所有满足性质 $\mathcal{P}$ 的语句的表达式，归纳基础和刚才的引理中 “包含 $\mathrm{Sent}_0$ ” 对应，归纳步骤则和 “运算封闭” 对应，从而根据引理可知归纳法成立. $\square$

## $L$ 语句的唯一可读性
对于一个 $L$ 语句，例如下面的表达式：
$$
(\neg p)\land (q\lor r)
$$
在我们阅读并拆分语句的时候，可以发现上面这个语句实际上可以分解为两个语句 + $\land$ ，这也就让我们思考是否每一个语句都能这样进行分解？并且是不是每个语句都只有唯一的分解方式？

事实上，对于命题语言，它必须能这样唯一分解，这种性质称为**唯一可读性**，如果没有这样的性质，语句可能产生歧义.

我们有如下的命题：

>[!note] 命题：命题语句的唯一可读性
>对于任意的 $L$ 语句 $\theta$ ，下列情形有且仅有一个成立：
>1. $\theta$ 是原子语句；
>2. 可以找到 $L$ 语句 $\varphi$ 使得 $\theta = \neg \varphi$ ，也就是 $\varphi$ 的否定.
>3. 可以找到 $L$ 语句 $\varphi$ 和 $\psi$ 使得 $\theta = \lor \varphi \psi$ ，也就是二者的析取.
>4. 可以找到 $L$ 语句 $\varphi$ 和 $\psi$ 使得 $\theta = \land \varphi \psi$ ，也就是二者的合取.
>5. 可以找到 $L$ 语句 $\varphi$ 和 $\psi$ 使得 $\theta = \to \varphi \psi$ ，也就是二者的蕴涵.
>6. 可以找到 $L$ 语句 $\varphi$ 和 $\psi$ 使得 $\theta = \leftrightarrow \varphi \psi$ ，也就是二者的双向蕴涵.
>
> 更近一步，对于 2~6 ，$\varphi$ 和 $\psi$ 是唯一确定的.

证明：利用**语句归纳法**.

分解为三个假定：
(1) 六个情形至少有一个成立.
(2) 六个情形至多有一个成立.
(3) 对于 2~6 ，$\varphi$ 和 $\psi$ 是唯一确定的.

由于我们使用的是前缀表达式的表达方法，(2) 假定显然是成立的，因为第一个符号就有所不同. 

----

对于假定 (1) ，考虑归纳证明，令表达式的性质 $\mathcal{P}$ 为 “六个情形至少有一个成立”.

对于 $n=1$ ，也就是原子语句的情形，情形 1 成立，归纳基础成立. 对于 $\varphi$ 和 $\psi$ 两个具有性质 $\mathcal{P}$ 的语句，此时加上一个二元连接词可以与 2~6 一一对应，加上 $\neg$ 则可与 1 对应，故命题成立. 

----

为了证明 (3) ，需要一个技术性的引理：

>[!info]+ 技术性引理及其证明
> 引入如下的引理：
> >[!note] 引理
> >对于任意有限的**符号序列** $\varphi_0,\cdots,\varphi_k$ 和 $\psi_0,\cdots,\psi_l$ **语句**，如果表达式 $\varphi_0\cdots \varphi_k$ 和 $\psi_0\cdots \psi_l$ 一致（注意此时是把这些语句放在一起形成一个新的表达式），则 $k=l$ 且对于 $i\leqslant k$ ，$\varphi_i = \psi_i$ .
>
> 
> 考虑定理的证明，也是使用语句归纳法.
>
> 归纳基础不必多说，对于更长的语句段，由于 (1) 和 (2) ，可以认为 $\varphi_0$ 满足 1~6 其中一个，如果 $\varphi_0$ 为原子语句，$\psi_0$ 就因而也只能是原子语句，从而将语句缩短为 $k-1$ 长度的语句，利用归纳假设可证明成立.
>
> 如果 $\varphi_0 = \neg \theta$ ，那么 $\psi_0$ 的第一个符号也必须是 $\neg$ ，从而 $\psi = \neg \chi$ ，此时去掉 $\neg$ 后我们将符号缩短了一位，归纳假设就可以使用了.
>
> 如果为二元连接词，写为 $\varphi_0 = \bullet \theta \theta'$ 和 $\psi_0 = \bullet \chi \chi'$ ，此时 $\theta \theta' \varphi_1 \cdots \varphi_k = \chi \chi' \psi_1\cdots \psi_l$ ，因此又可以使用归纳假设了. $\square$

现在我们使用引理证明 (3) ，根据引理，下面的式子：
$$
\bullet \varphi \psi = \bullet \varphi' \psi'
$$
能成立的条件就是 $\varphi = \varphi', \psi = \psi'$ ，从而命题成立. $\square$

## 语义与二值逻辑系统

刚才我们仅仅讨论了语句的**语法** (syntax)，下面讨论语句的**语义** (semantics)，当我们对原子语句赋值为真、假后，就能形成一个二值逻辑系统. 

(1) 对原子语句，可以设计一个映射，称为**真值指派** (truth assignment)，获得真假值：$V_0: \mathrm{Sent}_0 \to \left\lbrace \mathrm{T},\mathrm{F} \right\rbrace$ .
(2) 对于 2 阶及以上的语句，考虑连接词，且或非相对简单不再赘述，对于蕴涵关系：
$$
V(\to \varphi \psi) = 
\begin{cases}\mathrm{T},\text{if }V(\varphi) = \mathrm{F} \text{ or } V(\psi) = \mathrm{T};  \\
\mathrm{F},\text{Otherwise.}\end{cases}
$$
而 $\leftrightarrow$ 则在二者的真值相等时才为真，否则为假.

这里面的蕴涵真值表为：
$$
\begin{array}{ccc}
\varphi & \psi & \varphi\to \psi \\
\hline
\mathrm{T} & \mathrm{T} & \mathrm{T} \\
\mathrm{T} & \mathrm{F} & \mathrm{F} \\
\mathrm{F} & \mathrm{T} & \mathrm{T} \\
\mathrm{F} & \mathrm{F} & \mathrm{T}
\end{array}
$$
前面两行都比较好解释，但是后面两行其实比较反日常逻辑：你能想象假命题可以推出任何命题吗？这个矛盾称为**蕴含怪论**，无论什么解释实际上都会觉得与日常的逻辑相矛盾.

为了解决这个矛盾，我们在此暂且只认为它是一种二元真值算子即可，它等价于：
$$
p \to q \iff \neg p \lor q
$$

### 真值指派延拓

>[!note] 定理：真值指派的延拓
>每个原子语句的真值指派都有一个唯一的真值指派延拓.

首先对于原子语句 $p_0$ ，我们确定一个真值指派 $V_0(p_0)$ ，那么我们需要定义真值函数：
$$
V_{n} : \mathrm{Sent}_n \to \left\lbrace \mathrm{T},\mathrm{F} \right\rbrace
$$
那么我们给出如下的递归定义：
$$
V_{n+1}(\neg\varphi) =
\begin{cases}
\mathrm{T}, \text{if }V(\varphi) = \mathrm{F}; \\
\mathrm{F}, \text{Otherwise}.
\end{cases}
$$
$$
V_{n+1}(\varphi \land \psi) = 
\begin{cases}
\mathrm{T}, \text{if }V(\varphi) = \mathrm{T}  \text{ and } V(\psi) = \mathrm{T}; \\
\mathrm{F}, \text{Otherwise}.
\end{cases}
$$
或、蕴涵、双向蕴涵同理可写出表达式，这里不进行赘述.

此时我们能定义 $V: \mathrm{Sent}_L \to \left\lbrace \mathrm{T}, \mathrm{F} \right\rbrace$ ，其中 $V(\theta) = V_n(\theta)$ ，$\theta\in \mathrm{Sent}_n$ 但 $\theta\not\in \mathrm{Sent}_{n-1}$ . 因此存在性证明完毕.

对于唯一性，假设存在 $W_n$ 使得 $V_n(\varphi) = W_n(\varphi)$ ，那么在递归时：
$$
\begin{aligned}
V_n(\land\varphi\psi) &\iff V_n(\varphi) = \mathrm{T}\text{ and } V_n(\psi) = \mathrm{T} \\
&\iff W_n(\varphi) = \mathrm{T} \text{ and } W_n(\psi) = \mathrm{T} \\
&\iff W_n(\land \varphi \psi) 
\end{aligned}
$$
对于其他的连接词也类似，从而能证明 $V=W$ ，唯一性得证. $\square$

