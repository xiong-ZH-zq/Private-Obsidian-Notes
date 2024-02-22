---

aliases: 
date_creation: <% tp.date.now("YYYY-MM-DD") %>
word_root: 
type: en_word
---
TARGET DECK: Words::<% tp.system.prompt("请输入卡组") %>

<%* 
var title = tp.file.title
if (title.includes("Untitled")) {
var newTitle = await tp.system.prompt("请输入单词")
await tp.file.rename(newTitle)
}
-%>
START
Word Power
<% newTitle %>
音标: 
释义:
发音:
例句:
例句翻译:
拓展:
END