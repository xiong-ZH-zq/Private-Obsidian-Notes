---
type: math_note
date_creation: 2024-02-28
related_course:
  - "[[计算机集合论与逻辑 - 李军]]"
---
# The propositional language
## 集合计算与字符串表达式
我们在计算机集合论与逻辑中沿用我们以前曾学到的集合计算（交并补差、直积），因此不多做赘述.

对于可数个可数集 $X$ 的直积，我们约定符号 $X^{<\omega}$ 为可数个集合的直积. 如果我们在 $X$ 当中拥有的元素是字符，那么此时直积后得到的集合将会是**全体字符串的集合**. 

## $L$ 表达式与 $L$ 语句
### 符号集和表达式集
在有字符串的表示概念后，我们定义符号集：
$$
\mathrm{Symb} = \left\lbrace p_0,p_1,\cdots \right\rbrace\cup \left\lbrace  \neg,\vee ,\wedge ,\to ,\leftrightarrow \right\rbrace
$$
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

