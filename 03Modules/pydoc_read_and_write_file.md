## Reading and Writing Files

### 创建测试文件text-s.txt
> 内容为weather_info.txt的前三行

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

> 续写`a`不擦除原文件内容，`w`则会擦除。


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
> 一行一行地读，直到读完，之后的读取输出结果为None（null）。


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
> 读取全部行。


