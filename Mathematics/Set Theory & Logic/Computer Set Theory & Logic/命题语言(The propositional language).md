---
type: math_note
date_creation: 2024-02-28
related_course:
  - "[[计算机集合论与逻辑 - 李军]]"
---
# The Propositional Language
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
其中 $\neg$ 为**非**，$\lor$ 为**或**，$\land$ 为**且**，$\to$ 为**推导**(implies)，$\leftrightarrow$ 为**当且仅当**(If and only if). 这 $5$ 种符号称为**联结词**，而 $p_i$ 称为**语句符号**(sentence symbol).

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
>2. $\mathrm{Sent}_{n+1} := \mathrm{Set}_{n}\cup \left\lbrace \neg \varphi : \varphi\in \mathrm{Sent}_n  \right\rbrace\cup \left\lbrace \bullet \varphi \psi : \varphi, \psi\in \mathrm{Sent}_n \right\rbrace$  其中 $\bullet$ 为二元逻辑联结词；
>3. $\mathrm{Sent}_L := \displaystyle\bigcup_{n\in \omega}\mathrm{Sent}_n$ .
>
> $\mathrm{Sent}_L$ 中的元素，称为 $L$-**语句**.

对于 $L$-语句 $\varphi$ ，如果
$$
\varphi\in \mathrm{Sent}_n ,\varphi\not\in \mathrm{Sent}_{n-1}
$$
就称 $\varphi$ 为 $n$ 阶 $L$-语句.




## 语句归纳法与数学归纳法
下面给出语句归纳法的步骤：
>[!note] 定理：语句归纳法
>对于一个针对 $L$-表达式的性质 $\mathcal{P}$ ，如果：
> 1.  (归纳基础) 每个 $L$-原子语句都具有性质 $\mathcal{P}$ ；
> 2.  (归纳步骤) 如果 $\varphi$ 和 $\psi$ 都具有性质 $\mathcal{P}$ ，那么 $\neg \varphi$ 和 $\varphi\bullet \psi$ 都具有性质 $\mathcal{P}$ （其中 $\bullet$ 为二元联结词）；
> 
> 那么此时就能证明所有的 $L$-表达式都具有性质 $\mathcal{P}$ .

直接利用上面的引理即可. $\square$


## 语义与二值逻辑系统
下面讨论语句的**语义** (semantics)，当我们对原子语句赋值为真、假后，就能形成一个二值逻辑系统. 

(1) 对原子语句，可以设计一个映射，称为**真值指派** (truth assignment)，获得真假值：$V_0: \mathrm{Sent}_0 \to \left\lbrace \mathrm{T},\mathrm{F} \right\rbrace$ .
(2) 对于 2 阶及以上的语句，考虑连接词，且或非相对简单不再赘述，对于蕴涵关系：
$$
V(\to \varphi \psi) = 
\begin{cases}\mathrm{T},\text{if }V(\varphi) = \mathrm{F} \text{ or } V(\psi) = \mathrm{T};  \\
\mathrm{T},\text{Otherwise.}\end{cases}
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

