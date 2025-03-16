### 原文

```text
4 Ways to Check Which Shell You are Using on Linux

Last updated: July 29, 2022 | Winnie Ondara
Out of the box, Linux provides a wide variety of shells. There is bash (Bourne Again shell) shell which ships by default in many Linux distributions. We also have sh (Bourne Shell), tcsh (TC shell), csh (C shell), Zsh (Z shell) and ksh (Korn  Shell).

Curious to know which shell you are using on your Linux system? In this guide, we explore different ways that you can use to check which shell you are currently using in Linux.

1. Using echo command
The Linux echo command is a built-in command that is used to print the output of a string which is passed as an argument. Additionally, you can use the echo command to check the shell that you are running commands in. To accomplish this, execute:

$ echo $SHELL
Output of echo $SHELL
The output shows that I am using the bash shell. Additionally, you can simply run the command:

$ echo $0
Output of echo $0
To get the PID of the  shell that you are currently in, run:

$ echo $
Output of echo $$
2. Using ps command
Commonly used for listing running processes, the ps command in its basic format sheds light on the shell that you are using.  Simply execute the command:

$ ps
output of ps command
From the first line of the output, we can clearly see the PID of the shell and the last column prints out the type of shell, in this case - bash.

Alternatively, you can run the command:

$ ps -p $$
Output of ps -p $$
You can also use ps -p $$ -o args= which output just the shell name.

3. By viewing /etc/passwd file
The grep command can be used to probe the /etc/passwd file that contains attributes of the users such as username, user ID and group ID.

To display the shell used, invoke the command:

$ grep "^$USER" /etc/passwd
Using /etc/passwd file to show shell
At the very last segment, we get to see the bash used, in this case /bin/bash This also gives you a glimpse of which shell is opened first when you first log in to your system.

4. Using lsof command
Ordinarily, the lsof command, short for list of open files,  is used to provide a list of open files on your system. However, when used with the -p $$ flag, it gives a pointer to the shell you are in when you look at the first column of the output.

For example, we can clearly see that we are on the bash shell.

$ lsof -p $$
Output of lsof -p $$
How to check the valid login shells
We have seen various ways that you can employ to check the shell that you are currently in. If you want to know the valid shells on your system, check the /etc/shells file, This file will provide you with the full pathnames of valid login shells in your system. Using the cat command, view the file as shown:

$ cat /etc/shells
Valid login shells
Valid login shells
Conclusion
In this guide, we have shared simple but nifty ways that you can use to know which shell you are working on. This is important when writing scripts so that you can know how to start off writing the shebang header. We do hope that this tutorial was beneficial. Send us a shout and don't forget to share this guide on your social platforms.
```

### 常用搭配与短语 (Common Collocations)

####  `Out of the box`

* 字面意思"开箱即用"，指默认配置。

* 例句：`Linux provides a wide variety of shells out of the box.`

#### `Shed light on`

* 揭示、阐明某事。

* 例句：`The ps command sheds light on the shell you are using.`

#### `A glimpse of`

* 一瞥，简要了解。

* 例句：`...gives you a glimpse of which shell is opened first.`

#### `Nifty ways`

* 巧妙的方法（口语化表达）。

* 例句：`We have shared simple but nifty ways...`

#### `run the command` / `execute the command`

* 在技术文章中，用于提示读者输入特定的命令。

#### `output of`

* 用于说明命令执行后显示的结果，如 `Output of echo $SHELL`，直接指出输出内容的展示。

#### `using [command] command`

* 这种搭配用来说明采用哪个命令完成某项操作，如 `Using ps command` 或 `Using lsof command`

### 句式与语法分析 (Sentence Structures & Grammar)

#### 被动语态 (`Passive Voice`) 

* 用于强调动作本身而非执行者，常见于技术说明。

* 例句：
    * `The echo command is used to print...`
    * `The /etc/passwd file contains attributes...`

#### 条件句 (`Conditional Clauses`)

* 用于假设场景。

* 例句：`If you want to know the valid shells... check the /etc/shells file.`

#### 分词短语作状语 (`Participle Clauses`)

* 简化句子结构，增加信息量。

* 例句：
    * `Commonly used for listing processes, the ps command...`
    * `Ordinarily used to list files, the lsof command...`

#### 命令提示句型

* 例子：`To accomplish this, execute: $ echo $SHELL`

* 特点： 使用祈使句（`imperative mood`），直接给出操作指令，语气简洁明了。

### 语法解析

#### 时态使用

* 现在简单时：大部分描述和操作指令使用的是现在简单时（如 “Linux provides”, “You can use”），这是技术文档中常见的时态，适用于描述事实和常规操作。

#### 祈使句

* 用途：用于指导读者操作，如 “execute”, “run”, “invoke”。这类句子通常省略主语，直接使用动词原形。

#### 定语从句

* 例子：`that is used to print the output of a string which is passed as an argument.`

* 解析：通过定语从句提供额外信息，对主句中的名词进行修饰，是解释技术细节时常用的句型。