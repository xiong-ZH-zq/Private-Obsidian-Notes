---
type: code_note
date_creation: 2024-01-27
code_language: shell
---
# Shell 脚本

## 基本变量定义
```shell
foo=bar
echo $foo
>>>bar
```
在这里面，不能加空格，否则会被 shell 认为是 foo 命令.

基本变量的一个使用形式是在双引号当中输出：
```shell
foo=bar
echo "foo = $foo"
echo 'foo = $foo'
```
在双引号包围的内容中，`$` 后的变量会输出其值，而单引号则类似 Python 的 `r` 字符串，会直接输出 `$foo` 这个字符串.

## Shell脚本编写
### 创建和运行
创建一个 `mcd.sh` 的文件，并且输入以下的内容：
```shell
mcd(){
    mkdir -p $1
    cd $1
}
```
上述的脚本定义了一个函数，`$1` 表示第一个参数，这个脚本的含义是创建一个参数为名的文件夹并移动到文件夹当中.

使用 `source` 命令运行脚本：
```shell
source mcd.sh
# 或者使用 bash 和 zsh 运行脚本
zsh mcd.sh
```
此时就可以直接使用 `mcd` 命令了：
```shell
mcd test
```
我们就会发现，此时已经创建了一个 `test` 文件夹并移动了.

### 逻辑运算
对于 `$` 运算符，我们实际上还能有如下的用法：
- `$0` - 脚本名
- `$1` 到 `$9` - 脚本的参数。 `$1` 是第一个参数，依此类推。
- `$@` - 所有参数
- `$#` - 参数个数
- `$?` - 前一个命令的返回值
- `$$` - 当前脚本的进程识别码
- `!!` - 完整的上一条命令，包括参数。常见应用：当你因为权限不足执行命令失败时，可以使用 `sudo !!`再尝试一次。
- `$_` - 上一条命令的最后一个参数。如果你正在使用的是交互式 shell，你可以通过按下 `Esc` 之后键入 . 来获取这个值。

需要注意的是这里的 `bool` 值和想象中的是相反的. 例如
```zsh
true
echo $?
```
得到的结果将会是 `0` . 对于 `false` 则是 `1` .

在 `$()` 的括号当中输入一些命令可以实现输出命令结果的效果.
```shell
$ echo "We are in $(pwd)"
We are in /home/xzqbear/missing
```

逻辑运算符和 C 的是基本一致的，例如 `||` 为或运算. 但是这里由于 shell 普遍为命令执行，实际上对于逻辑运算应该这么理解：
- 对于逻辑与 `&&` ，应该理解为 **如果这个命令执行成功&&就执行这个命令** .
- 对于逻辑或 `||` ，也就是相反的**如果这个命令执行失败 || 那么就执行这个命令**.

除此之外还有一些特殊字符，例如 `;` 为连续运行命令.

