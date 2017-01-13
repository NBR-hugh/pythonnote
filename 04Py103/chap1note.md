# 1w个人教程
  
  
## <a name = "目录"></a> 目录
* [核查清单](#核查清单)
	* [勿犯错误](#勿犯错误)
	* [编程建议](#编程建议)
* [本章任务](#本章任务)
* [任务计划](#任务计划)
* [尝试过程](#尝试过程)
* [反思改进](#反思改进)
* [问题提出](#问题提出)
* [参考来源](#参考来源)





## <a name = "核查清单"></a> 核查清单


### <a name = "勿犯错误"></a> 勿犯错误


>- 错误0：花了太多时间学习那些不是特别重要的东西上。
	- 启示：专注于任务和与任务有关的内容，时刻问自己：这和当前的任务有关联吗？
- 错误1：没有立即开始写代码

### <a name = "编程建议"></a> 编程建议


#### 制作原型知识方法

>1. 动手跟着教程做一些编码例子。
2. 找一个简单的项目，开发它。
3. 反复执行第#2条多次。
4. 开发出自己的应用。

#### 阳老师的编程四建议
>1. 注重内隐知识
2. 将语言与逻辑分开，不断在头脑中进行逻辑预演
3. 使用执行意图而非目标意图
4. 成为一名认知学徒，教别人执行

[返回目录](#目录)



## <a name = "本章任务"></a> 本章任务


### 完成一天气查询程序
> 1. 任务要求
2. 功能实现
3. 实现效果
4. 任务资源

#### 1. 任务要求：
>1. 程序运行在命令行界面；
2. 通过命令行与程序实行交互来实现查询天气等功能。

#### 2. 功能实现
>1. 输入城市名，获取该城市的天气情况。
2. 输入指令，获取帮助信息。
3. 输入指令，获取历史查询信息。
4. 输入指令，退出命令行的程序。

#### 3. 实现效果

```
$ python demo_1w_task.py
请输入指令或者您要查询的城市名称：北京
北京的天气状况为：晴
请输入指令或者您要查询的城市名称：贵港
北京的天气状况为：小雨
请输入指令或者您要查询的城市名称：help
		
		输入城市名，查询该城市的天气；
		输入 help，获取帮助文档；
		输入 history，获取查询历史；
		输入 quit，退出天气查询系统。
		
请输入指令或者您要查询的城市名称：history
北京 晴

贵港 小雨

请输入指令或者您要查询的城市名称：quit
$ 
```

#### 4. 任务资源
> - [weather_info.txt](https://github.com/AIMinder/Py103/tree/master/Chap1/project)

[返回目录](#目录)







## <a name = "任务计划"></a> 任务计划

> （之后添加的内容符号为++）

### 明确任务

- 记录[任务](#本章任务)，并做整理。

### 分析任务

#### 输入和输出是什么？

* 文本的输入（程序内部进行）。
* 命令行界面的输入与输出。
	1. 城市名 --> 该城市天气
	2. help --> 帮助信息
	3. history --> 查询历史信息
	4. quit/exit --> 退出程序（广义上的输出）

#### 应该如何连接输入和输出？
>请给出多种方案！或在完成MVP后再探索。

1. .txt -> list -> dict
	1. file相关的[Reading、Writing命令](#读写文件)。
	2. 如何读取行?
		1. readlines
		2. readline
		3. list(file），然后对list操作，转到dict中？（太繁琐？）
		4. 更加简单直接的？
	3. 如何对行进行切割？
		1. 用for?

			```		
			for i in range(len(line)): 
				if line[i] == ',':
					bef_comma = line[:i]
					aft_comma = line[i:]
			```
		2. 有没有更加直接的方法？			
			
2. help -> 帮助信息：
	1. 函数
	2. 字符串变量
	3. 直接print()
3. history -> 查询历史信息	
	2. 新建一个dict、list、var
	3. 新建一个文件，如csv格式文件，再读出。
4. quit -> 退出程序
	1. quit() 
	2. break（++）

#### 最基本的方案是什么？
- 先尝试以上的内容，做出完整运行的程序，然后优化之。


#### 拟定初步方案1
* 检索：file -> list -> dict
* help：调取函数
* history: list.append()
* quit：quit()

#### 需要学习哪些内容？
* dict
	* `__name__`的意义？
* file
* list
* string
* 还有没有我没有注意到的知识点？

#### 学习计划
* 确定此次需要的功能：
	* 即上述列出的知识点和初步的设想。	

#### 有没有其他方案？
* 比起原来的方法有什么不同？
* 更加简单了？复杂了？高效了？衡量的方式是？
* 能否编出用户友好的交互模式？
* 能否使输出更为丰富？

#### 后续优化
* 去掉原版本中一切冗余环节。
	* 从file直接到dict
	* 没有必要的中介变量
	* 这里不用函数调用help信息，除非在程序中调用多次。
	* 寻找我没有发现的**可供性**
		- 例如string.split()（++）
		- dictionary[key]=value（++）

#### 同伴资源
* 观察记录  

[返回目录](#目录)

## <a name = "尝试过程"></a> 尝试过程

[Reading and Writing Files]()
[dict使用](https://vygibe.gitbooks.io/pyhthonnote/content/03Modules/pydoc_dict.html)

 
 
[返回目录](#目录)

## <a name = "反思改进"></a> 反思改进


如果我重新做这个任务，我会如何做？

1. 明确问题，分析问题，拆解问题。
	2. 任务内容是什么？详细记录任务。	
	3. 提供了什么参考资源？是否都需要看？
	4. 哪些是必看，哪些是之后可参考使用？为什么这样分（与我的任务是否有关，而且是高相关）？
	4. 明确输入和输出，在纸上画出，标出。
	5. 明确基本的程序流、分支、环路，画出草图。

	> 不要跳过分析部分就直接开始处理问题（除非问题很简单）。

1. 利用之前已经学到的知识技能。
	2. 哪些知识是我已知的？
		2. list了解较多，如list的index功能，slicing功能。
		3. dict粗糙记得些，如{key: value}的格式。
		4. string的简单操作。
		5. file的基本的开闭、读写。
	3. 目前的知识是否足够完成输入与输出的对接？
	4. 还需要哪些知识？参考资料的使用？
	3. 动手做一个初级产品。
	> 写代码。

2. 试验过程中对旧知识进行复习，对新知识进行扩展。记录错误和改正方式。
	3. 当前学习使用什么知识点？隶属什么范畴？和我的任务有关系吗？和长期的编程有关吗？
	4. 它如何运作?
	5. 为什么它可以运作？
	6. 它是否有效地实现了我的目的？有没有偏离我的目的？有没有更好的方法？
	
3. 完成初期产品后，对产品进行多种修改，阅读和试验更多同一类型的`输入->输出`的实现方式，优化其结构。
	4. 代码表现最简版。
	5. 多知识点运用版。
	6. 多功能实现版。
	6. 交互友好版。
	6. 运算最少版。
	7. 内存使用最少版。  

[返回目录](#目录)


## <a name = "问题提出"></a> 问题提出


1. 大妈或者教练们会用什么基本方法完成这个程序？如果他们写出了一个，我和他们有什么区别？我能从中学到什么?
2. 其他学员在事先不同功能时，都用了什么方式？我能学到什么，我如何在这次的修改完善中运用起来？

## <a name = "参考来源"></a> 参考来源

> - 读取天气数据：Python 读写文件参考<a name = "读写文件"></a>
[Reading and Writing Files](https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files)
- 把天气数据转换为字典 
	- [Mapping Types — dict](https://docs.python.org/3.5/library/stdtypes.html#typesmapping)
 	- [Data Structures](https://docs.python.org/3.5/tutorial/datastructures.html#data-structures)
 	- [Looping Techniques](https://docs.python.org/3.5/tutorial/datastructures.html#looping-techniques)
- 使用中文和程序进行交互：[字符串和编码](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/001431664106267f12e9bef7ee14cf6a8776a479bdec9b9000)
- [极简Python上手导念](http://wiki.zoomquiet.io/pythonic/MinimalistPyStart?from=timeline&isappinstalled=0)
- ch1 BGM 推荐 [Marvin the Album](http://music.163.com/#/album?id=260676)
- 彩蛋：大妈聊初学编程的最大错误
- [The 2 Biggest Mistakes I Made When Learning to Code](http://www.suneelius.com/2012/09/07/the-2-biggest-mistakes-i-made-when-learning-to-code/)[(译文)](http://www.vaikan.com/the-2-biggest-mistakes-i-made-when-learning-to-code/)
- [How I Taught Myself to Code in 8 Weeks](http://tech.yipit.com/2012/08/21/how-i-taught-myself-to-code-in-8-weeks/)

[返回目录](#目录)

