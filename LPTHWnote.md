## ex. 02
#### 1. 注释和 “#” 符号  
见[“#”的功]能](#anchor1)

#### 2. 检查代码的方法：  
倒序阅读、出声朗读

### ex. 03 
#### 基本的数字运算
###### 加减乘除  
	
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
	
	 
###### 比较大小
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
###### 取余 “ % ”

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
######“print a, b”中“,”的意义
	
	>>> print 1, 1 + 2, 3
	1 3 3

###ex. 04
变量及命名
    定义变量
练习注释
“ == ”的意义
数学运算公式的输入易读性

###ex. 05
变量的命名和赋值
    命名规则
搜索所有字符串格式化符号
使用round()

###ex. 06
字符串和文本
    变量命名原则：尽量不要极简缩写
学会使用并区分%s、%d、%r
字符串含有%s、%d、%r
    变量赋值
    替换或赋值
    一一对应关系
字符串的 ” + ” 运算

###ex. 07 
出错后的解决方式
单引号和双引号的使用
    输入时
    输出时
    
###ex. 08
逗号在 print 中起到的作用
初识布尔代数

###ex. 09
转义字符
针对出误的建议
三引号的作用

###ex. 10
转义字符
while
for
建议使用flash cards
有些问题可在之后解决，但前提是记录下来

###ex. 11
raw_input() 的使用，及和input的差别
逗号在放在连续的 print 间的用法
int() 的使用
写代码讲究文本在视知觉上的组织（空行）

###ex. 12
raw_input([prompt]) 使用
在 Terminal 中 pydoc 命令的使用
    查询open, os, file, sys
    
###ex. 13
argument
from … import …
argv 和raw_input() 的差别

###ex. 14
raw_import([prompt])

###ex. 15 
读取文档
functions/methods
网络搜索关键词用法“python THING”：

###ex. 16 
Terminal 中退出python的方法
    1. ^Z
    2. quit()
以“ w ”打开文件，以及其他打开方式。
open()默认打开方式
fileobject.write()
fileobject.truncate()

###ex. 17
import的使用及官方文档中的说明
os.path exists()
cat 
len()
en()
