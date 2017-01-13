## 学习内容
 
### 目录
	
-  Reading and Writing Files
	- 建立测试文件，测试file相关的读取操作。
		- open
			- mode
		- read
		- readline、readlines、list(file)
-  list
	- 尝试截取list中的string的字符。 
		- 有split(',',5)这样的方法，后面的数字可有可无，有表明截几次。（++）
-  dict
	- 见知识块中的[dict]()
	

## Reading and Writing Files

### 创建测试文件text-s.txt
内容为weather_info.txt的前三行

	北京,晴
	海淀,晴
	朝阳,晴

### 打开文件 - open()

`open(filename,mode)`

#### 其中mode有以下5种：

`'r'` - 只读，默认状态（即open(filename)的状态）  
`'w'` - 只写  
`'r+'`- 可读可写  
`'a'` - 续写  
`'b'` - 二进制形式打开  

### 测试open()：

```
$ touch file.py
$ open file.py
```

### 文件内容导入file


``` 
file = open('test.txt','r')
print(file)
``` 

### 运行

```
$ python file.py
<_io.TextIOWrapper name='test.txt' mode='r' encoding='UTF-8'>
```

> 可见文件被打开，其mode为'r'，encoding为UTF-8

### 读取文件

#### 使用.read()

```
file = open('test-s.txt','r')
print(file.read())
print(not file.read())
print(file.read())
```
##### 输出结果

```
$ python file.py
北京,晴
海淀,晴
朝阳,晴
True

```

> 第二个print(file.read())并没有读出内容，因为其内容为None，也即前一次已将文本读完。

#### 测试.readline()

```
file = open('test-s.txt','r')

print(file.readline()) # 读第一行
print(file.readline()) # 读第二行
print(file.readline()) # 读第三行
print(file.readline()) # 继续读下一行
```

##### 输出结果

```
北京,晴

海淀,晴

朝阳,晴

```

#### 测试.readlines()

```
file = open('test-s.txt','r')
print (file.readlines())
```
##### 输出结果

```
北京,晴

海淀,晴

朝阳,晴

```



# 列表

### 使用列表解析

```
file = open('test-s.txt','r')

for line in file:
	print (line, end = '')
```

### 使用list()

```
file = open('test-s.txt','r')

print (list(file))
```

##### 结果

```
$ python file.py
['北京,晴\n', '海淀,晴\n', '朝阳,晴\n']
```




### 尝试截取list中的每一个字符
#### 先尝试index功能。

```
>>> ls=['朝阳,晴\n']
>>> len(ls)
1
>>> len(ls[0])
5
```

#### 然后打印出每单个字符

```
>>> for i in len(ls[0]):
...     print(ls[i])
... 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'int' object is not iterable
```
> 出错原因，in之后的应该是list类型，而不是一个数值。

>>> for i in range(len(ls[0])):
...     print(ls[i])
... 
朝阳,晴

Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
IndexError: list index out of range
>>> for i in range(len(ls[0])):
...     print(ls[i,i+1])
... 
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
TypeError: list indices must be integers or slices, not tuple
>>> for i in range(len(ls[0])):
...     print(ls[i:i+1])
... 
['朝阳,晴\n']
[]
[]
[]
[]
>>> for i in range(len(ls[0])):
...     print(ls[0][i:i+1])
... 
朝
阳
,
晴


```

```
>>> for i in range(len(ls[0])):
...     a = ls[0][i:i+1]
...     print("%r" % a)
... 
'朝'
'阳'
','
'晴'
'\n'
```

设想：`,`之前的string全部给
`,`之后的string全部给 

```
ls = ['朝阳,晴\n']

for i in range(len(ls[0])):
	a = ls[0][i: i + 1]     
	if a == ',':
		bef_comma = ls[0][:i]
		aft_comma = ls[0][i+1:]
		break
	print(i)

print(bef_comma, aft_comma)
```

创建dict

```
dict_weather = dict([(bef_comma, aft_comma)])
```
批量化

```
file = open('test.txt','r')

ls = list(file)
file.close()

newlist = []

for j in range(len(ls)):
	for i in range(len(ls[j])):
		a = ls[j][i: i + 1]     
		if a == ',':
			bef_comma = ls[j][:i]
			aft_comma = ls[j][i+1:]
			newlist.append((bef_comma, aft_comma))
			break
```

创建分支

```
while True:
	cityname = input('请输入指令或者您要查询的城市名称：')

	if dict_weather.__contains__(cityname):
		print(cityname, dict_weather[cityname])
		history.append([(cityname, dict_weather[cityname])])
	elif cityname == 'help':
		func_help()
	elif cityname == 'history':
		for i in range(len(history)):
			print(history[i][0][0],history[i][0][1])
	elif cityname == 'quit':
		quit() 
	else:
		continue
```

将前后连贯起来完成初期作品：


出现的错误

if语句后的冒号

判断等于为==  

```
$ python 1w_task.py
Traceback (most recent call last):
  File "1w_task.py", line 22, in <module>
    dict_weather.update((bef_comma, aft_comma))
ValueError: dictionary update sequence element #0 has length 3; 2 is required
```

.update({key: value})


```
>>> b = {'one': 1, 'two'=2, 'three'=3}
  File "<stdin>", line 1
    b = {'one': 1, 'two'=2, 'three'=3}
                        ^
SyntaxError: invalid syntax
```

字典里key和value的mapping用:

```
>>> c = dic(zip(['one','two','three'], [1, 2, 3]))
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'dic' is not defined
```

小错误不断啊，练习太少的缘故。

```
>>> e = dict({'three':3,'one‘: 1,'two':2})
  File "<stdin>", line 1
    e = dict({'three':3,'one‘: 1,'two':2})
                                    ^
SyntaxError: invalid syntax
```
中英文符号是大伤，怎么解决？用command + space切换输入法。


```
d = {'three':3,'one‘: 1,'two':2}
>>> clear(d)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'clear' is not defined

```

应该使用d.clear()


```
>>> d.items()[1]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'dict_items' object does not support indexing
```

```
>>> d.popitem(('one',1))
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: popitem() takes no arguments (1 given)
```

```
>>> d = {'two': 2, 'one': 1, 'three': 3}
>>> d.update(('five',5))
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: dictionary update sequence element #0 has length 4; 2 is required
>>> d.update('five',5)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: update expected at most 1 arguments, got 2
>>> d.update(['five',5])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: dictionary update sequence element #0 has length 4; 2 is required
```


有没有在read file状态下close file的必要？

研究string的截取，list，dict的操作。


自己创造一些任务：

技能导师：

在CLI界面实现

技能的流程

技能步骤的指令

我是怎么做的？

品质的评价

反思

下一个技能步骤

写一个程序，改编这个程序的程序？

编写一个程序来完善我的笔记记录。
