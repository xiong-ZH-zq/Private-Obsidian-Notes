---
type: Code_Card
date_creation: 2024-02-29
code_language: shell
---

TARGET DECK: Code::shell

START
Programming
我觉得每次打 `cd ~/obsidian/mydata` 都比较烦，如何简化其变成 `ob` 命令？
Back: 
```shell
alias ob="cd ~/obsidian/mydata"
```
Addition: 
需要注意的是，只有把这个内容写到 `~/.bashrc` 或者 `~/.zshrc` 才能默认生效，否则只能在当前的终端生效.
<!--ID: 1709140675802-->
END