# 安装第三方库，以Pygame举例

## 安装pip
- [教程地址](https://pip.pypa.io/en/stable/installing/)

## 安装pygame
- 出错以及解决：
	
直接用`python setup.py`导致如下错误
	
```
src/pygame.h:106:10: fatal error: 'SDL.h' file not found
#include <SDL.h>
         ^
1 error generated.
error: command 'clang' failed with exit status 1
```
如下代码可实现安装

```
brew install sdl sdl_image sdl_mixer sdl_ttf portmidi
pip install https://bitbucket.org/pygame/pygame/get/default.tar.gz
```

	