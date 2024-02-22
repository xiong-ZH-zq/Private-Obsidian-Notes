---
type: theorem_card
date_creation: 2024-01-30
related_book:
---
TARGET DECK: Math::概率论::Theorem

START
基本问答
Recall non-naive definition of probability.
答案:
A **Probability Sample** consists of $S$ and $P$, where $S$ is a sample space and $P$ is a function which takes an event $A\subset S$ as input, returns $P(A)\in [0,1]$ as outputs such that:
1. $P(\varnothing) = 0$ , $P(S)=1$ .
2. $\displaystyle P\left(\bigcup_{n=1}^\infty A_n\right) = \sum\limits_{n=1}^\infty P(A_n)$ if $A_j$ are disjoint.
笔记:
None
相关知识:
[[Havard Stat 101 Lecture 2#Non-naive Probability Axioms]]
<!--ID: 1706581608528-->
END