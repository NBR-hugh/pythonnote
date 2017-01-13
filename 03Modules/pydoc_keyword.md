# Python-Keyword

### 查看keywords list
```
$ python
>>> import keyword
>>> $ keyword.kwlist
['and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'exec', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'not', 'or', 'pass', 'print', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

### 关键字总结

#### if、elif、else：

```
if_stmt ::= "if" expression ":" suite
            ( "elif" expression ":" suite )*
            ["else" ":" suite]
```

> 若`if`之后的`expression`为`True`，则执行其后的`suite`，跳过其他判断的`suite`，  
若`if`之后的`expression`为`False`，则判断`elif`之后的`expression`；  
若某`elif`之后的`expression`为`True`，则执行其后的`suite`，跳过其他判断的`suite`  
若该`elif`之后的`expression`为`False`，则执行`else`之后的`suite`。  

###### e.g.

```
# -*- coding: utf-8 -*-
print "我们来完猜数字的游戏吧！",'\n',"请输入一个数字来猜猜我给的数字是多少！"

while True:

	num = int(raw_input("请输入一个数字! > "))
	
	if num == 31:
		print "恭喜您，猜对了！"
		break
	elif num > 31:
		print "大了~"
	else:
		print "小了~"
```
#### while、break、continue:

```
while_stmt ::= "while" expression ":" suite
               ["else" ":" suite]
```

> 若`while`后的`expression`为`True`，则循环地执行之后的`suite`，  
若该`suite`中，`break`被执行，则终止当前的`while`循环，  
若该`suite`中，`continue`被执行，则跳过当前`while`循环中的后续语句，重新检验`expression`，  
若`while`后的`expression`为`False`，则可执行`else`后的`suite`，并终止该循环。

> 小结：`continue`忽略其后的`suite`，`break`终止当前的`while`。

###### e.g.
```
# -*- coding: utf-8 -*-

num = 3

i = 0 
j = 0

# 测试while和else中else的用法1
print "测试while和else中else的用法1"

while num > i:
	i += 1
	print "while"  
else:
	print "else"

# 测试while和else中else的用法2
print "测试while和else中else的用法2"

while False:
	print "while"
else:
	print 'else'
	
# 测试while中break及continue的用法
print "测试while中break及continue的用法"

while True:
	print "while"
	j += 1
	
# 测试break
	if j > 4:
		print "j > 4 break "
		break	``
# 测试continue	
	if j > 2:
		print "continue", j
		continue
	if j > 2:
		print "break", j
		break
```

### for
```
for_stmt ::= "for" target_list "in" expression_list ":" suite
             ["else" ":" suite]
```

###### e.g.
```
ls = [1,4,3,5,6,7,8,0]

# test the keyword "else"
for i in ls:
	if i > 2:
		print i
else:
	print "The list is exhausted."
	
# test the keyword "break"	
for i in ls:
	if i > 2:
		print i
	if i > 3:
		print 'break'
		break
else:
	print "The list is exhausted."	
```

### and、or、not

`and` `or`

```
x and y
x or y
not x
```
> ###### 对于`and`先算`x`，`x`为`False`，返回结果为`False`，若`x`为`True`，则还需判断`y`。

```
>>> 0 or 3
0
>>> 2 and 3
2

```

> ###### 对于`or`先算`x`，`x`为`True`，返回结果为`True`，若`x`为`False`，则还需判断`y`。

```
>>> 2 or 3
2
>>> 0 or 3
0

```

> - "False", "None", numeric zero of all types, and empty strings and containers 
> - (including strings, tuples, lists, dictionaries, sets and frozensets).  
> - All other values are  interpreted as true.


###### e.g.

```
T = True, F = False

print T and T , T and F, F and T, F and F
print T or T , T or F, F or T, F or F
print not T, not F
```

**结果**

```
True False False False
True True True False
False True
```
### is、is not

> 比较两个值是否相等

###### e.g. 

```
>>> 0 is 0
True
>>> 0 is 1
False
>>> (1,1) is (1,1)
False
>>> [0] is [0]
False
```

```
>>> 1 is not 1
False
>>> 1 is not 0
True
```

###in

> 判断某对象是否在某字符串、元组、列表等中。

```
>>> "1" in "123"
True
>>> 1 in [1,2,3]
True
>>> 1 in (0,1)
True
>>> 1 in (0,2)
False
>>> 1 in [2,3]
False
```