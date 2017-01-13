# Git使用教程（仅针对Mac系统）

## 1. 安装与配置
### 1.1 安装
- 从官方下载安装包安装
[点击下载](https://sourceforge.net/projects/git-osx-installer/files/git-2.10.1-intel-universal-mavericks.dmg/download?use_mirror=autoselect)

### 1.2 运行Git前的配置
#### 1.2.1 **使用`git config`工具设定用户信息**

```
$ git config --global user.name "John Doe"   
$ git config --global user.email johndoe@example.com
```    
#### 1.2.2 设定TextWrangler为默认文本编辑器

1. 点击菜单栏中的`TextWrangler`>`Install Command Line Tools`，进行安装。

2. 再在终端输入如下命令：


```
git config --global core.editor "edit --wait --resume "$@""
	
```
#### 1.2.3 设定解决合并冲突时的差异分析工具

```
$ git config --global merge.tool vimdiff
```
> Git 可以理解 kdiff3，tkdiff，meld，xxdiff，emerge，vimdiff，gvimdiff，ecmerge，和 opendiff 等 合并工具的输出信息。

#### 1.2.4 查看配置信息

- 查看所有配置信息

```
$ git config --list
```
**Or**  

```
$ git config -l
```
- 查看某一特定的配置信息

```
$ git config user.name
John Joe
```
#### 1.2.5 获得帮助

```
$ git help <verb>
$ git <verb> --help
$ man git-<help>
```
**e.g.**

```
$ git help config
```
## 2. 基本使用
### 2.1 克隆
> 若是本地新建文件夹，用`git init`命令。

克隆在线仓库

	git clone https://github.com/VyGiBe/test
	git clone https://github.com/VyGiBe/test anyname

第二行是给新建库自命名

### 2.2 查看当前文件状态

	$ git status
	On branch master
	Your branch is up-to-date with 'origin/master'.
	nothing to commit, working tree clean

简短显示

```
git status -s
```


### 2.3 跟踪新文件

新建一文件，查看其状态，其为untracked file状态。

```	
$ touch test.md
$ git status 
	On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	test.md

nothing added to commit but untracked files present (use "git add" to track)	
```
跟踪指定文件：

```
git add test.md
```

跟踪所有未跟踪文件，用`.`代替之上的文件名称：

```
git add .
```
再次查看结果，可见其已被跟踪：

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   test.md

```
### 忽略某些文件

- 在使用`git add .`时，可能会跟踪类似`.python_version`、`.DS_Store`等文件，当它们并没有用时，需要将其忽略。  
- 可以在根目录新建一个`.gitignore`文件，并在Terminal中打开，输入需要忽略的规则，具体可见[Pro Git官方文档](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)。

### 比较差异

查看修改之后还没有暂存起来的变化内容：

```
git diff
```
查看已经暂存起来的文件和上次提交时的快照之间的差异：

```
git diff --cached
```


### 提交更新

确定提交更新，使用`commit`命令。

```
$ git commit
```
并使用TextWrangler编辑commit。

推荐可以用`git commit -a -m "<commmit>"`完成`add`和`commit`，以跳过使用暂存区域。






## 进阶使用
## 附录
## 参考来源