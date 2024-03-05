---
type: choice_card
date_creation: 2024-02-12
tags: 
code_language: mysql
---

TARGET DECK: Code::MySQL

START
Select
在 MySQL 中，下列表达式哪一个不报错且结果为 100 ？
Choices:
`'99'+'1'`<br>`100+NULL`<br>`100-'1'`<br>`('b'-'a')+99`
Back:
- MySQL 中的 `+` 不存在“字符串连接”这样的含义，因此字符串参与相加都会尝试隐式类型转换.
- `'a'` 等无法转换的字符， MySQL 直接视为 0.
<!--ID: 1707748214507-->
END