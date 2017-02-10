# 第五周个人教程

这一周，你是这样探索的：

## 1. 查看“开智学堂”卡包信息

卡包是脚手架。
如果仅仅是自己探索，其自由度过大，离偏离目标的可能性也会增加。
而充分利用起卡包内的资源，可以减少自由度，不至于太偏离目标。
引申出来便是寻找“好的导师”，获得减少无意义探索的指引。
完成本周MVP任务，回顾卡包的内容。

1. 卡包提供及提及的基本信息：
    2. 作为Web框架的Flask，用以实现浏览器和服务器的交互。
        3. GET and POST
    3. HTML基本知识。
    4. Templates 懒人开发。
        5. Jinja2
            - 模板的基本结构
            - 变量的表示
            - 循环
            - 判断
            - 模板继承  
    4. CSS
        - 美化页面 
    5. Bootstrap 
        - 优化页面以适配移动端。 
    5. 如何看技术文档（例子！！！）：
        6. 大妈如何看技术文档；
        7. 新手应该如何看技术文档：@CallingCrab的技巧。
    8. 本周的任务描述和实现效果。
    9. 接触新功能，建议跑个MVP来体验实现效果，然后理解每一行的功能和意义，可以通过看文档、改参数、删除等等方式来理解。
    10. 复用之前成果。 

## 2. 记录自己不懂的内容
- 内网、公网
- Web、HTML、CSS、Web框架
- Flask


## 3. 分解任务

##### 知识和相应目的之间的关联：

* HTML、CSS --> 生成、制作网页
* Flask --> 服务器和浏览器的交互
* Jinja2 --> 制作模板，减少重复劳动

## 4. 开始动手

### 学习Flask
1. 查看官方文档；
2. 运行MVP。

##### 分析示例代码

1. 示例代码：
    
    ```
    (1)    from flask import Flask     
        
    (2)    app = Flask(__name__)       
        
    (3)    @app.route('/')             
    (4)    def helloworld():           
    (5)        return "Hello World!"   
        
    (6)    if __name__ == "__main__":  
    (7)        app.run(debug=True)     
    ```
2. 实现方式 `python hello.py` 
3. 命令行信息
    
    ```
    (08)    $ python hello.py                                   
    (09)     * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
    (10)     * Restarting with stat     
    (11)     * Debugger is active!      
    (12)     * Debugger pin code: 870-990-949   
    (13)    127.0.0.1 - - [07/Feb/2017 19:58:00] "GET / HTTP/1.1" 200 -     
    ```

3. 实现效果：
  <h3>Hello World!</h2>
4. 逐句分析
    
- (01) 导入flask库中的Flask类。

- (02) 创建程序实例，并初始化Flask，Flask只有一个必须输入的参数；用来确定程序的根目录，以便找到相对于根目录的资源文件的位置。

        In [1]: from flask import Flask

        In [2]: app = Flask(__name__)
        
        In [3]: app
        Out[3]: <Flask '__main__'>
    > 表明app是Flask的一个实例，或是Flask类的对象，如果文件以顶层程序文件执行，在启动时，`__name__`就会设置为字符串"`__main__`"。
    
    `__name__`作为实例变量，其值为主程序模块或包的名字，它是每个模块的内置属性，例如：
        
        In [1]: import math
        
        In [2]: math.__name__
        Out[3]: 'math'
    > 据我实验，还可以是函数的名字，甚至匿名函数如`(lambda x : x*2).__name__`为`'<lambda>'`，但数值、字符串、列表、词典变量没有该属性
    


- (03) app.route为修饰器，它是python的标准特征，其功能是：
    1. 修改函数的行为；
    2. 将函数注册为事件的处理程序。
        - 这里的app.route起路由的作用，它是处理URL和函数之间关系的程序，产生相应的URL到python函数的映射（路由，即从此地到彼地，必经之路、由）。
        - URL - Universal Resource Locater，统一资源定位符，俗称网页地址。
        - 其中的`'/'`表明将之后的`index`函数注册为程序根目录（hello.py保存的目录）的处理程序，在该目录下`index()`才起作用。
    3. 研究一个修饰器：
    
            class tracer 
        
        
        
        > 示例代码来自《Python学习手册中文第三版》
- (04) 视图函数（view function） 用以返回含HTML的字符串、复杂表单等，它接收客户端的请求，并向服务器发出请求。
* (05) `index()`的返回值，又称为响应。  
* (06) 用以确保直接执行这个脚本时才启动开发Web服务器；若其他脚本引入，则不会执行`app.run()`。@faketooth建议不要使用`flask run`运行方法，而采用这一方法。
* (07) 启动服务器，进入轮询（类似警察对犯罪嫌疑人编号轮番询问？），debug=True表示在开发模式下，打开“调试”。如果报错，其结果会显示在网页上，同时也会显示在
* (08) 运行hello.py脚本。
* (09) 显示本地服务器的地址，`127.0.0.1`可用`localhost`代替，按下`CTRL + C`退出已启动的服务器。
* (10) --
* (11) 调试器被启动。
* (12) --
* (13) 127.0.0.1 为服务器地址；GET为request所用的method，200是返回响应状态码（表示请求成功），还有404，500，400（请求无效）等状态码。HTTP/1.1为传输协议及其版本号，HTTP/1.1支持持续连接。


### 学习HTML
1. 示例代码

    ```    
    (01)  <! DOCTYPE html>
    (02)  <html>
    (03)      <body>
    (04)          <h1>My first line!</h1>
    (05)          <p>Hello world!</p>
    (06)          <br>
    (07)          <form>
    (08)              输入用户名:<br>
    (09)              <input type=“text” name=“username”><br>
    (10)              <input type=“password” name=“password”>
    (11)          </form>
    (12)      </body>
    (13)  </html>
    ```

* (01) 声明文档类型为HTML。

* (02) 定义HTML文档，以`<html>`开始，`</html>`终止。
* (03) 定义文档体，以`<body>`开始，`</body>`终止。
* (04) 标题，有h1-h6(markdown就是用html实现的)。
* (05) 段落，以`<p>`开始，`</p>`终止。
* (06) 插入`break`，此处最右边用了`<br>`进行换行，👉<br>在markdown中`<br>`独立占一行则空两行或者在有语句行中起回车键的功能，在句子最后，则空一行。
    
    ```    
    第一行
    <br>
    第二行
    第三行<br>
    第四行
    ```
        
##### 实现效果

***
第一行
<br>
第二行
第三行<br>
第四行
***

* (07) 定义表单，以`<form>`开始，`</form>`终止。

* (08) 见(06)。
* (09) `<input>`类型，用户可以输入以发送请求，可以设定`tpye`、`name`、`value`键的键值。
* (10) 同上。
* (11) `<form>`的End Tag
* (12) `<body>`的End Tag
* (13) `<html>`的End Tag

更多内容：




### 学习客户端和服务器的通信
##### 目标通信方式
- 表单中的文本信息馈入Flask中的视图函数，并馈入天气查询系统。
    
    - 从flask中导入request。
    - 在表单内即`<form>...</form>`使用`<input>`，先生成一个输入框，然后生成提交按钮，按下该按钮后，使用`input_text = request.form['text01']`获取输入框中的值。  
    <input type="text" name="text01" value="在此输入城市名~"> <input type="submit" name="search" value="搜索">
    
    - 生成历史、帮助按钮。
    <input type="submit" name="history" value="历史"> <input type="submit" name="help" value="帮助">

    - 一字排开的效果：
    <input type="text" name="text01" value="在此输入城市名~"> <input type="submit" name="search" value="搜索"> <input type="submit" name="history" value="历史"> <input type="submit" name="help" value="帮助">
    
    - 代码：
    
        ```
        <input type="text" name="text01" value="在此输入城市名~"> 
        <input type="submit" name="search" value="搜索">      
        <input type="submit" name="history" value="历史">      
        <input type="submit" name="help" value="帮助">
        ```
    
- 表单中按下按钮，馈入Flask视图函数。
  
    > 我在这里遇到了坑，原因应该是我所用的搜索关键词不恰当。最后把错误诊断完全拷贝入google搜索，获得的解答完全可以解决我的问题。

    - 因为一共要接受3种触发按钮，查到可用三个判断语句。语句的基本格式为`request.form['\<name>'] == '\<value>'`。

- 天气查询系统返回查询信息，馈入视图函数并给出响应，发送给服务器，服务器在浏览器内给出信息显示。
    - 天气查询系统只要复用上周的成果便可以。
        - 此处遇到的坑是之前编写上周代码时，不是事先规划如何编写类，而是边写边改。
        - 解决方案：下次编写类，定要事先规划。
        
            > 编程，即计划（劃）、计画（畵）。
            `program`，`pro-`：向前，`-gram`：写、画。
            `programmer`，事件规划员、事件计划员。
            `event`，所发生的、所出现的、所呈现的，`e-`：`out`。
    - 在浏览器内显示原搜索页面的同时，显示天气信息兼历史帮助信息。
        - 使用Jinja2。
            - 使用模板。
            - 使用变量。
            - 先从从flask中导入render_template。
 
            
- 对应的按钮信息，视图函数给出相应的响应，发送给服务器，服务器在浏览器内给出信息显示。

### 学习Jinja2
> Jinja为模板引擎。

#### 试验最简模板

##### 文件位置：

- `templates/index.html`

##### 文件文本：

- `<h1>Hello World!<h1>`

##### 实现代码： 
```
from flask import render_template
...
@app.route('/')
def view_function():
   render_template('index.html') 
```

##### 实现效果：

<h1>Hello World!</h1>

#### 基模板

```
        <html>
        <head>
(01)        {% block head %}
(02)        <title>{% block title %}{% endblock %} - My Application</title> 
(03)        {% endblock %}
        </head>
        <body>
(04)        {% block body %}
(05)        {% endblock %}
        </body>
        </html>
```

- (01) 基模板中的head模块，`以{% block <blockname>%}`开始，`{% endblock %}`结束。

- (02) 基模板中的title模块
- (03) 见(1)。
- (04) 基模板中的body模块。
- (05) 见(1)。

#### 衍生模板

```
(01)    {% extends 'base.html' %}
        {% block title %}Index{% endblock %}
        {% block head %}
(02)            {{ super() }}
(03)            <style>
                </style>
        {% endblock %}
        {% block body %}
        <h1>Hello, World!</h1>
        {% endblock %}
```

- (01) 继承`base.html`模板。

- (02) 使用super()描绘parent block。
- (03) 


#### 变量

    `{{ name }}`

- 以上为变量，其中`{{  }}`为占位符，`name`为变量名。
- Jinja能识别的变量名有：
    - `mydict['key']`
    - `mylist[3]`
    - `mylist[myintvar]`
    - `myobj.somemethod()`

##### 使用：

显示天气用`{{ displayWeather }}`变量，在返回值中，先使用模板，再给模板内的displayWeather变量赋值，用视图函数将其呈现在查询结果页面。

在模板内嵌入`{{ displayWeather }}`，然后在视图函数内如此返回：

```
return render_template('weather_frame.html')
```


#### 控制语句
> 原理同Python。


    {% if statment %}
        {{ name }}
    {% elif statment %}    
    {% else %}
        {{ name }}
    {% endif %}    
    

#### 循环语句
> 原理同Python。

    {% for listitem in alist %}
        {{ listitem }}
    {% endfor %}
    
#### 模板继承
- 见**衍生模板**


### 学习HTML和CSS其他功能

- 初步只需要实现一种功能：
<center>居中!做到了！</center>
- 代码：

    ```
    <center>居中!做到了！</center>
    ```    

### 学习部署

> 尚未开始



