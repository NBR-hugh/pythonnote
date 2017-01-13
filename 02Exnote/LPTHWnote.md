# ex. 01  
#### 1. `print`的使用
*(先运行`print`后内容，再将运行内容的结果输出)*
  
	>>> print "string"
	string
	>>> print 'string'
	string
	>>> print 12345
	12345
	>>> a = 'string'
	>>> print a
	string
	>>> print a + a
	stringstring
	>>> print a * 3
	stringstringstring   

#### 2. 字符串的输出  
	
	>>> print "I am writing this script."
	I am writing this script. 
	>>> a = 'aaa'
	>>> print a, 'a'
	aaa a
#### 3. 在 Terminal 中运行 python 文件；

	python ex01.py
#### 4. 报错的解读；  
	
	>>> print "I am writing this script." "
	File "<stdin>", line 1
    print "I am writing this script." "
                                      ^
	SyntaxError: EOL while scanning string literal
- 1 运行的文件路径和名称(运行文件时)  
- 2 出错的行  
- 3 ^（脱字号）指出行中具体发生错误的位置  
- 4 给出错误的原因  
	
#### 5. ASCII 编码及中文的输出设定；

- 如果要输出中文，需在开头写下：  

```
# -\*- coding: utf-8 -*-
```
#### 6. [`#` 的功能](id:anchor1)  
*`#` 表示注释，之后的代码不会被执行*

- 注释的用处：  
	1. 使该部分代码的功能失用  
	2. 说明这部分代码的用处  

# ex. 02
#### 1. 注释和 “#” 符号  
见[“#”的功能](#anchor1)

#### 2. 检查代码的方法：  
倒序阅读、出声朗读

# ex. 03 
#### 基本的数字运算
##### 加减乘除  
	
	>>> 1 + 1
	2
	>>> 1 - 1
	0
	>>> 1 * 1
	1
	>>> 1 / 1
	1
 *注意浮点数和整数在 “/” 运算中的区别*
 	
	>>> for i in xrange(6):
	...     i += 1
	...     print "7 / %r = %r" % (i,7/i)
	... 
	7 / 1 = 7
	7 / 2 = 3
	7 / 3 = 2
	7 / 4 = 1
	7 / 5 = 1
	7 / 6 = 1
	>>> 1 / 4
	0
	>>> 1.0 / 4
	0.25
	>>> 1 / 4.0
	0.25
	>>> 1.0 / 4.0
	0.25
	
	 
##### 比较大小
	>>> print 4 < 4
	False
	>>> print 4 > 4
	False
	>>> print 4 == 4
	True
	>>> print 4 <> 4
	False
	>>> print 4 <= 4
	True
	>>> print 4 <= 5
	True
	>>> print 4 <= 3
	False
	>>> print 3 >= 3
	True
	>>> print 3 => 3
	  File "<stdin>", line 1
	   print 3 => 3
	          ^
	SyntaxError: invalid syntax
##### 取余 “ % ”

	>>> for i in xrange(9):
	...     i += 1
	...     print "13", "%", i, "=", 13 % i
	... 
	13 % 1 = 0
	13 % 2 = 1
	13 % 3 = 1
	13 % 4 = 1
	13 % 5 = 3
	13 % 6 = 1
	13 % 7 = 6
	13 % 8 = 5
	13 % 9 = 4
##### “print a, b”中“,”的意义
	
	>>> print 1, 1 + 2, 3
	1 3 3

### ex. 04
变量及命名  
    定义变量  
练习注释  
“ == ”的意义  
数学运算公式的输入易读性  
 
### ex. 05
变量的命名和赋值  
    命名规则  
搜索所有字符串格式化符号  
使用round()  

### ex. 06
字符串和文本  
    变量命名原则：尽量不要极简缩写  
学会使用并区分%s、%d、%r  
字符串含有%s、%d、%r  
    变量赋值  
    替换或赋值  
    一一对应关系  
字符串的 ” + ” 运算  

### ex. 07 
出错后的解决方式  
单引号和双引号的使用  
    输入时  
    输出时  
    
### ex. 08
逗号在 print 中起到的作用  
初识布尔代数  

### ex. 09
转义字符  
针对出误的建议  
三引号的作用  

### ex. 10
转义字符  
while  
for  
建议使用flash cards  
有些问题可在之后解决，但前提是记录下来  

### ex. 11
raw_input() 的使用，及和input的差别  
逗号在放在连续的 print 间的用法  
int() 的使用  
写代码讲究文本在视知觉上的组织（空行）  

### ex. 12
raw_input([prompt]) 使用  
在 Terminal 中 pydoc 命令的使用  
    查询open, os, file, sys  
    
### ex. 13  
argument  
from … import …  
argv 和raw_input() 的差别  

### ex. 14
raw_import([prompt])  

### ex. 15 
读取文档  
functions/methods  
网络搜索关键词用法“python THING”：  

### ex. 16 
Terminal 中退出python的方法  
    1. ^Z  
    2. quit()  
以“ w ”打开文件，以及其他打开方式。  
open()默认打开方式  
fileobject.write()  
fileobject.truncate()  

### ex. 17
import的使用及官方文档中的说明  
os.path exists()  
cat   
len()  
en()  

## Ex.18 Names, Variables, Code, Functions

## 核查清单(函数)：
***
###### 写一函数时

1. Did you start your function deﬁnition with def? 
2. Does your function name have only characters and _ (underscore) characters? 
3. Did you put an open parenthesis ( right after the function name? 
4. Did you put your arguments after the parenthesis ( separated by commas? 
5. Did you make each argument unique (meaning no duplicated names)? 
6. Did you put a close parenthesis and a colon ): after the arguments? 
7. Did you indent all lines of code you want in the function four spaces? No more, no less. 
8. Did you “end” your function by going back to writing with no indent (dedenting we call it)? 

###### 用一函数时
1. Did you call/use/run this function by typing its name? 
2. Did you put the ( character after the name to run it? 
3. Did you put the values you want into the parenthesis separated by commas? 
4. Did you end the function call with a ) character?



## 函数
***
#### 概念理解
- 黑箱比喻。

#### 函数的三种功能

1. They name pieces of code the way variables name strings and numbers.   
	命名小段代码。  
2. They take arguments the way your scripts take argv.   
	喂入(携带)参数。  
3. Using # 1 and # 2, they let you make your own “mini-scripts” or “tiny commands.”  
	上述功能可使得自己能编写小指令集。

#### 定义过程[^1]

```
def function(argv):
	<statement>
```	

[^1]:括号中可以没有参数  



## Q & A
***
  

Q - `def`的意义？  
A - define的缩写，声明开始定义函数。

  

Q - `argv`这一缩写的意义？  
A - argument vector


  

Q - `*argv`中的`*`的意义？   
A - That tells Python to take all the arguments to the function and then put them in args as a list.


  

Q - 为什么函数会给出None的值   
A - 因为函数中没有return相应值

  

Q - 缩进和代码运行之间的关系？   
A - [Python: Myths about Indentation](http://www.secnetix.de/olli/Python/block_indentation.hawk)

  

Q - 函数名的命名原则   
A - 和变量名命名方式一致


	
## 出错
***
### 错误一  

```
$ python ex18.py
  File "ex18.py", line 15
    def print_none()
                   ^
SyntaxError: invalid syntax
```
处理  

```
def function(): # 注意之后的“:”
```
### 错误二  

```
$ python ex18.py
  File "ex18.py", line 25
    Study Drills
               ^
SyntaxError: invalid syntax
```
处理  

- 应该加上 `#` 符号，

### 出错三



	def add_strings(strings):
		result = ""
		for i in strings:
			result += i
		print result	
		
	strings = ["aaa","bbb","ccc"]
	print add_strings
	
	<function add_strings at 0x100a15c80>

处理  

	print add_strings(strings)

### 出错四

	$ python ex18.py
	  File "ex18.py", line 29
		for i in strings:
	    ^
	IndentationError: unexpected indent

处理  

- 因为在函数内按了两下**Tab**，导致不能运行。
- 减少一个缩进


## Ex.19 Functions and Variables



## 本练习内容概要
***
#### 调用函数时  
1. 可直接赋值  
2. 可将值赋给变量，然后将变量带入函数  
3. 可在函数的()内进行数字的运算  
4. 可在函数的()内进行数字和变量的复合运算  


#### 函数中的变量和代码中的变量相隔离
###### 举例

	def function(arg):
		var = arg
		return var

	var = "I am a variable"
	result = function("It is different from 'var'!")
	
	print var, "\n", result, "\n"
	print result, "\n", var, "\n"
	
	result = function("It is different from 'var'!")
	var = "I am a variable"	 
	
	print var,"\n" ,result, "\n"
	print result, "\n", var, "\n"
	
	I am a variable 
	It is different from 'var'!
	
	It is different from 'var'! 
	I am a variable
	
	I am a variable 
	It is different from 'var'!
	
	It is different from 'var'! 
	I am a variable


## Q & A
***
Q - 如何理解一个函数时如何运作的？  
A - （1. 上方加注释； 2. 出声朗读； 3. 将代码打印出，用图画出，并注释如何运行。 ）
> There’s many different ways, but try putting an English comment above each line describing what the line does. Another trick is to read the code out loud. Yet another is to print the code out and draw on the paper with pictures and comments showing what’s going on.  

Q - 什么是global variables？  
A - 
> In computer programming, a global variable is a variable with global scope, meaning that it is visible (hence accessible) throughout the program, unless shadowed. - From [Wikipedia](https://en.wikipedia.org/wiki/Global_variable)

Q - 定义函数时，参数个数有限制吗？   
A - 有，但该值还是很大的

Q - 能在函数内调用函数吗？   
A - 可以


# ex 27 逻辑

## 真值项

`True` - 逻辑真  `False` - 逻辑假

## 逻辑运算符

- and - 合取
- or - 析取
- not - 否定
- != - 不等
- == - 相等
- \> - 大于
- \>= - 大于等于
- < - 小于
- <= - 小于等于


# ex 28 布尔逻辑运算

## 运算方法

1. 比较式用真值代替。
2. 先运算括号内的式子。
3. 每一not都获得其后式子相反的真值。
4. 找到任何还剩余的`and/or`，并解出。
5. 最终会获得真值。

### 发现：
```
>>> not 1
False
>>> not None
True
>>> not ['a']
False
>>> not (1,2)
False
>>> not (0,0)
False
>>> not []
True
>>> not {1:4}
False
```

### 解释:
```
$ pydoc not 
```

> In the context of Boolean operations, and also when expressions are
used by control flow statements, the following values are interpreted
as false: "False", "None", numeric zero of all types, and empty
strings and containers (including strings, tuples, lists,
dictionaries, sets and frozensets).  All other values are interpreted
as true.

# Ex 29 if
> 这不就是`执行意图`吗？ 
> 学习编程还要学习给自己的行为进行编程。  
- 人与计算机的交互：本次学习的第一层次目的  
- 人与他人、自己的交互：本次学习的第二层次目的  

```
$ pydoc
```

```
The "if" statement is used for conditional execution:
   if_stmt ::= "if" expression ":" suite
               ( "elif" expression ":" suite )*
               ["else" ":" suite]            
```

- if_stmt: if语句
- suite: 指令集
- ()*: 表示可以有无数句。
- []:可以有但只有一句。

x += 1 为 x = x + 1  
x -= 1 为 x = x - 1  

## 出错
```
$ python test.py
  File "test.py", line 5
    if dogs = 10:
            ^
SyntaxError: invalid syntax
```
- 出错原因

== 才是进行判断的符号

= 是赋值符号


# Ex 30

```
num = input("输入一个数字")
```

```
python ex30.py
输入一个数字98
Traceback (most recent call last):
  File "ex30.py", line 3, in <module>
    if num >= 20:
TypeError: '>=' not supported between instances of 'str' and 'int'
```

# Ex 31

本章内容 if elif 和else

if 满足条件就执行其后的语句
elif 之前的if或elif的条件没有满足，就判断下一个elif的条件是否满足，
else 若之前的if和elif（若有）的条件都不满足，且有else，则执行else后的语句。

if语句中嵌套if语句。


## 出错

```
$ python ex31.py
  File "ex31.py", line 7
    print（ "There's a giant bear here eating a cheese cake. What do you do?"）
         ^
SyntaxError: invalid character in identifier
```

`print`后需要紧随`(`

```
$ python ex31.py
  File "ex31.py", line 7
    print( "There's a giant bear here eating a cheese cake. What do you do?"）
                                                                            ^
SyntaxError: invalid character in identifier
```

中文括号总是报错，
解决方法
在运行前，使用替换。

```
$ python ex31.py
  File "ex31.py", line 25
    print("3. Understanding revolvers yelling melodies.")
        ^
SyntaxError: invalid syntax
```

之前的一个print其后没有`)`


### 问题：若input()向int() 里馈入了字符串，出现报错，怎么让他重新输入？

先判断input了什么类型的输入。
如果是int，则继续，否则令其重新输入。
if type()

```
try:
   val = int(userInput)
except ValueError:
   print("That's not an int!")
```

```
>>> try print("a")
  File "<stdin>", line 1
    try print("a")
            ^
SyntaxError: invalid syntax
```


# Ex 32

本章内容 列表和for


	