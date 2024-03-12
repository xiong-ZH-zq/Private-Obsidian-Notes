---
type: math_note
date_creation: 2024-03-06
related_course:
  - "[[计算机集合论与逻辑 - 李军]]"
---
# 命题语义(Propositional Semantics)
## 永真式（重言式）与语义等价
首先先证明一个简单的命题，对于 $L$-语句 $\varphi$ ，若有两个真值指派 $V$ 和 $W$ ，那么对于任意 $\varphi$ 中语句符号 $p_n$ ，若恒有 $V(p_n) = W(p_n)$ ，则记为 $V = _{\varphi}W$ ，有如下命题：

>[!note] 命题
>对于每一个语句 $\varphi$ 和任意真值指派 $V$ 和 $W$ ，如果 $V = _{\varphi}W$ ，那么 $V(\varphi) = W(\varphi)$ .



### 永真式和语义等价
>[!note] 定义：永真式、语义等价
>(1) 如果对于语句 $\varphi$ ，在所有的真值指派下 $V(\varphi) = \mathrm{T}$ 恒成立，则称 $\varphi$ 为**永真式**(tautology) ，记为 $\mid\!\equiv \varphi$ .  如果 $\neg \varphi$ 为永真式，则 $\varphi$ 为**永假式**.
>
>(2) 若对任意的真值指派 $V$ 都有 $V(\varphi) = V(\psi)$ ，则称 $\varphi$ 和 $\psi$ 是**语义等价**（重言等价）的. 记为 $\varphi \mid\!\equiv\!\mid \psi$ .
>
>(3) 若对任意的真值指派 $V$ ，如果 $V(\varphi) = \mathrm{T}$ ，则 $V(\psi) = \mathrm{T}$ ，那么就称 $\psi$ 为 $\varphi$ 的**语义后承**(tautological consequence) . 记为 $\varphi \mid\!\equiv \psi$ .

从定义可以立即导出：
- $\varphi\mid\!\equiv\!\mid\psi$ 当且仅当 $\mid\!\equiv \varphi\leftrightarrow \psi$ .
- $\varphi\mid\!\equiv \psi$ 当且仅当 $\mid\!\equiv \varphi\to \psi$ .



### \*常见的永真式、语义后承与语义等价
在数理逻辑（乃至哲学）上，我们有以下的常见表达式：
- 排中律：$\mid\!\equiv \varphi\lor \neg \varphi$ （这个是我们能使用反证法的逻辑基础）
- 矛盾律：$\mid\!\equiv \neg (\varphi\land \neg \varphi)$ .
- 双重否定表肯定：$\varphi \mid\!\equiv\!\mid \neg\neg \varphi$ .
- 分类讨论：$(\varphi\to \chi )\land (\psi\to \chi)\mid\!\equiv (\varphi\lor \psi)\to \chi$ .

## 

>[!note] 定义
>$\mathrm{Sent}_{\neg \lor}$ 是包含原子语句的、在 $\neg$ 和 $\lor$ 运算下封闭的最小集合. 

>[!note] 命题：$\mathrm{Sent}_{\neg \lor}$ 是等价于 $\mathrm{Sent}_L$ 的
>对所有的语句 $\varphi$ ，总有 $\varphi^*\in \mathrm{Sent}_{\neg \lor}$ 使得 $\varphi\mid\!\equiv\!\mid \varphi^*$ .

这个命题说明了实际上只需要 $\neg$ 和 $\lor$ 就足够了. 为了证明这个命题，实际上

