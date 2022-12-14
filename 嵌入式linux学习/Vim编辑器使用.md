# Vim编辑器使用

```vim
$vim 文件名 
```

基本上vi/vim共分为三种模式，分别是命令模式、输入模式和末行模式。

## 命令模式

- 用户一启动vim便进入了命令模式
- 用户可以通过i、a、o、O等简单字母进入编辑模式
- 用户输入`:`可进入末行模式。

## 输入模式

- 在输入模式中，可以使用以下按键：
- - 字符按键以及shift组合，输入字符
  - ENTER，回车键，换行
  - BACKSPACE，退格键，删除光标前一个字符
  - DEL，删除键，删除光标后一个字符
  - 方向键，在文本中移动光标
  - HOME/END，移动光标到行首/行尾
  - Page Up/Page Down,上/下翻页
  - Insert，切换光标为输入/替换模式，光标将变成竖线/下划线
  - ESC，退出输入模式，切换到命令行模式

## 末行模式

- 在命令模式下按下`:`就进入了末行模式
- 底线命令模式可以输入单个或多个字符
- 按ESC可退出命令行模式

## vim按键说明（常用）

### 一般模式可用的光标移动、复制粘贴、搜索替换

#### 移动光标的方法

0或功能键[home]					#移动到这一行最前面字符处

$或功能键[end]						#移动到这一行的最后面字符处

G												#移动到这个档案的最后一行

nG											#n为数字.移动到这个档案的第n行（可配合:set nu）

gg												#移动到这个档案的第一行

n[Enter]									#n为数字。光标向下移动n行

#### 搜索替换（常用）

/word								#向光标之下寻找一个名称为word的字符串

?word								#向光标之上寻找一个字符串名称为word的字符串

n										#这个n是英文案件。代表重复前一个搜寻的动作。

:n1,n2s/word1/word2/g			#n1 与 n2 为数字。在第 n1 与 n2 行之间寻找 word1 这个字符串，并将该字符串取代为 word2

**:1,$s/word1/word2/g** 或 **:%s/word1/word2/g**			#从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2

**:1,$s/word1/word2/gc** 或 **:%s/word1/word2/gc**		#从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2 ！且在取代前显示提示字符给用户确认 (confirm) 是否需要取代

#### 删除、复制与粘贴

x, X								#在一行字当中，x 为向后删除一个字符 (相当于 [del] 按键)， X 为向前删除一个字符(相当于 [backspace] 亦即是退格键)

dd									#剪切游标所在的那一整行

ndd								#n 为数字。剪切光标所在的向下 n 行

yy									# 复制游标所在的那一行

nyy								#n 为数字。复制光标所在的向下 n 行，例如 20yy 则是复制 20 行

p,P								#p 为将已复制的数据在光标下一行贴上，P 则为贴在游标上一行

**u**									#复原前一个动作

[ctrl]+r							#重做上一个动作（感觉像重复上上一个命令光标位置所做的动作）

### 一般模式切换到指令行模式的可用的按钮的说明(常用)

:w								#将编辑的数据写入硬盘档案中

ZZ								#如果修改过，保存当前文件并退出

ZQ								#不保存，强制退出。

### vim环境的变更

:set nu						#显示行号，设定之后，会在每一行的前缀显示该行的行号

:set nonu					#取消行号