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

	
## 出错
***
### 错误一  

处理


