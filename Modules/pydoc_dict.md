# dictionary

[官方文档网址](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)


描述
语法
参数
返回值
实例




功能|函数|功能|函数
-----|----|----|----
字典化|dict(obj)|长度|len(d)
检索key的value|d[key]|删除特定{key:value}|del d[key]
判断key是否在d中|key in d|判断key是否在d中|key not in d 或 not key in d
删除全部内容|d.clear()|获得d的简单拷贝|d.copy()
|||


在词典中，不建议用浮点数，因为它是近似数。

形式{key: value}

```
class dict(**kwarg)
class dict(mapping, **kwarg)
class dict(iterable, **kwarg)
```
上面三句是什么意思？

class又是什么意思？

**呢？


key必须是唯一的吗？是的。

实验：

```
>>> test = {2:4}
>>> test
{2: 4}
>>> test[2] = 5
>>> test
{2: 5}
```
> 原有的key对应的value被替换。

五种返回同一dict的方法

```
>>> a = dict(one=1, two=2, three=3)
>>> b = {'one': 1, 'two': 2, 'three': 3}
>>> c = dict(zip(['one', 'two', 'three'], [1, 2, 3]))
>>> d = dict([('two', 2), ('one', 1), ('three', 3)])
>>> e = dict({'three': 3, 'one': 1, 'two': 2})
>>> a = b = c = d = e
True
```
len()

```
>>> d = dict([('two', 2),('one', 1), ('three', 3)])
>>> len(d)
3
```
d[key]

```
>>> d = dict([('two', 2),('one', 1), ('three', 3)])
>>> d['two']
2
```

del d[key]

```
>>> del d['one']
>>> d
{'two': 2, 'three': 3}
```
key in d

```
>>> 'one' in d
False
```

key not in d ; not key in d

```
>>> 'one' not in d
True
>>> not 'one' in d
True
```

clear()

```
>>> d
{'two': 2, 'three': 3}
>>> d.clear()
>>> d
{}
```
copy()

```
>>> d.copy()
{'two': 2, 'one': 1, 'three': 3}
```

fromkeys(seq[, value])

```
>>> d.fromkeys(range(3),3)
{0: 3, 1: 3, 2: 3}
>>> d
{'two': 2, 'one': 1, 'three': 3}
```
get(key[, default])

```
>>> d.get('one')
1
>>> d.get('four')
>>> print(d.get('four'))
None
>>> d
{'two': 2, 'one': 1, 'three': 3}
```

items()

```
>>> d.items()
dict_items([('two', 2), ('one', 1), ('three', 3)])
```

keys()

```
>>> d.keys()
dict_keys(['two', 'one', 'three'])
```

values()




pop()

```
d = {'two': 2, 'one': 1, 'three': 3}
>>> d.pop('one')
1
>>> d
{'two': 2, 'three': 3}
```

popitem()

```
>>> d = {'two': 2, 'one': 1, 'three': 3}
>>> d.popitem()
('three', 3)
>>> d
{'two': 2, 'one': 1}
```

setdefault(key[,default = None])

```
>>> d = {'two': 2, 'one': 1, 'three': 3}
>>> d.setdefault('four',4)
4
>>> d.setdefault('five')
>>> d
{'two': 2, 'one': 1, 'three': 3, 'four': 4}
{'two': 2, 'one': 1, 'three': 3, 'four': 4, 'five': None}
```

update()

```

```