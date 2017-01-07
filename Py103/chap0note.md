# 0w个人教程

#### 目录

- 本章任务
- 计划
- 入门参考
- 选择参考
- 差异比较
	- 各版本发布信息
	- 版本使用建议
	- Ex01 Ex 31 测试print
	- Ex03 测试/的用法
	- Ex05 测试Unicode - 中文变量名
	- Ex32 range用法

## 本章任务：探索Python3.X与Python2.X的不同

- 在LPTHW中选3-7个练习，用Python3.X改写之
- 将发现的不同之处记录到个人教程中，告诉六个月前的自己


## 计划

1. 差异的分类
	2. 整体的差别
	3. 细节的差别
2. 聚焦0w任务
	3. 内容不能太多。不是要“研究”python，而用它实现我需要的结果。
		- 原则：少而精
	4. 可以搜集在表明两者差异的网站，为以后有所需了便能参考。
	5. 不必列举目前阶段较少用到的差别。
	6. 列举之前的编程练习中两版本的差异，以及之后几周可能会用到的那些功能。
		7. 找出练习01-17中能典型反映出两者差异的练习。
		8. 猜测之后几周的编程中会使用到什么新功能。
			9. Python中基础的内容是什么？
			10. Python中核心的内容是什么？
3. 教程撰写计划
	- What - 有什么差别？- 难度较低 **知识要点**
	- How - 差别是怎么样的？写几行代码给我看看！- 难度中等 **技能重点**
	- Why - 为什么会有这样的差别？- 难度大 **有余力可以研究**
		- 可以查询官方文档，包括PEP。
		- 开发者的解释 - 有哪些重要的开发者，他们的博客、Twitter？
		- 可以提出自己的猜想
	- 目的：写代码过程及撰写教程的过程中，整合卡片中的一些理念。
		- 最小模型的迭代“进化”，运用反省智力，充分利用经验。
			- 有哪几个最小模型？
				- `设想--尝试--失败--搜索`循环
				- `小黄鸭调试法`
		- 及时记录在学习过程中出现的主要问题、进展和成就。
			- 自己就是程序员和计算机，自我调试。	





## 入门参考内容
-	 [官方文档](https://www.python.org/doc/)
-	[Hitchhiker](http://docs.python-guide.org/en/latest/)



## 选择参考的内容
1. [官方文档](https://www.python.org/doc/)
	- 选择其中较为重要，且常常使用到的差别进行比较。
		- 整体差别 
			- [What are the differences?](https://wiki.python.org/moin/Python2orPython3#What_are_the_differences.3F)
		- 具体差别 
			- [Writing Python 2-3 compatible code](http://python-future.org/compatible_idioms.html)
			- [python2转为python3的方法](https://docs.python.org/3/library/2to3.html#to3-reference)   
			> 最能体现两者在具体语法层面上的差别。
	- 选择有代表性的几个ex来探讨两者的差别。
2. 程序员大牛对两者的评价
3. 第三方机构对Python两个版本的测评


## 差别比较

### [各版本发布时间信息](https://www.python.org/downloads/)

|版本类型|最早版本|发布时间|最新版本|发布时间|
|:-|:-|:-|:-|:-|:-|
|Python 2.X|Python 2.0.1|2001-06-22|Python 2.7.13|2016-12-17|
|Python 2.7.X|Python 2.7.0|2010-07-03|Python 2.7.13|2016-12-17|
|Python 3.X|Python 3.0.0|2008-12-03|Python 3.6.0| 2016-12-23|

> 其中，Python 2.7.X 的支持将持续到[2020](https://hg.python.org/peps/rev/76d43e52d978)年。

### 版本使用建议
- [Should I use Python 2 or 3?](https://wiki.python.org/moin/Python2orPython3)

> 废话不多说了，直接coding来显示其差别！

## Ex01 Ex 31 测试print在python 3.6.0 下的运行
### What

- 2.X中的`print`在3.X中为`内建函数`。

### How

2.7.10下

```
>>> print "string"
'string'
```
3.6.0下

```
>>> print("string")
'string'
```

#### 发现
在python 2.7.10下, `print()`也能被运行。

在python 2.7.10下，`pydoc print`，有如下信息:

```
   print_stmt ::= "print" ([expression ("," expression)* [","]]
                  | ">>" expression [("," expression)+ [","]])
```


而在python 3.6.0中，它直接成了`Built-in Function`

```
print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
```
### Why 

[PEP 3105 -- Make print a function](https://www.python.org/dev/peps/pep-3105/)


## Ex03 测试/的用法

#### What

由实验Ex01，print()在两版本中都可用，在不同版本中，运行如下语句：

```
print(3 + 2 + 1 - 5 + 4 % 2 - 1 / 4 + 6) #鸡蛋的数目
```

`python 2.7.10`下

```
7
```

`python 3.6.0`下

```
6.25
```

#### Why

个人猜想：  
`1 / 4 = 0`的运算结果，获得小数点还必须在运算的数字中加小数点，对日常计算，增加了不必要的负担。Python若要追求人机交互的效能，应去掉它。

## Ex05 测试Unicode - 中文变量名

#### What-何为Unicode？

- Unicode（中文：万国码、国际码、统一码、单一码）是电脑科学领域里的一项业界标准。它对世界上大部分的文字系统进行了整理、编码，使得电脑可以用更为简单的方式来呈现和处理文字。 Unicode涵盖的资料除了视觉上的字形、编码方法、标准的字符编码外，还包含了字符特性，如大小写字母。- [Wikipedia](https://zh.wikipedia.org/zh-hans/Unicode)

#### How

1. 若在.py文件中输出中文，不需要`# -*- coding: utf-8 -*-`这一行了。 
2. Unicode标准的文字可以用作变量名，如下所示：

```
>>> 零 = 0
>>>print(零)
0
```


#### Why-为何使用Unicode?

> Supporting Unicode and text from any written language is important. Python is a language for the world, not just for those languages that support the Roman alphabet that ASCII covers.   
 --  Tall, Snarky  [Why Python 3 exists](https://snarky.ca/why-python-3-exists/)


## Ex 32 3.X中xrange用range表示，2.X的range功能被xrange()代替

### What
python 2.X中，range(10)会产生一个列表，  
而xrange(10)则不是，它是以xrange object的形式存在。  

在python 3.X中，输入下列代码：  

### How
 
```
>>> for i in xrange(10):
...     print(i)
... 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'xrange' is not defined
```
可见，xrange被取消。

### Why

[PEP 260 -- Simplify xrange()](https://www.python.org/dev/peps/pep-0260/)