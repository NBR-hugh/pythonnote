# range的用法
```
 range(stop) -> range object
 range(start, stop[, step]) -> range object
```
```
Return an object that produces a sequence of integers from start (inclusive)
 to stop (exclusive) by step.  range(i, j) produces i, i+1, i+2, ..., j-1.
 start defaults to 0, and stop is omitted!  range(4) produces 0, 1, 2, 3.
 These are exactly the valid indices for a list of 4 elements.
 When step is given, it specifies the increment (or decrement).
```




range(9)


```
>>> for i in range(9):
...     print( i)
... 
0
1
2
3
4
5
6
7
8
```

```
>>> for i in range(6,9):
...     print( i)
... 
6
7
8
```

```
>>> for i in range(-4,9,3):
...     print( i)
... 
-4
-1
2
5
8
```

```
>>> for i in range(9,-4,-3):
...     print( i)
... 
9
6
3
0
-3
```


```
>>> range(10).count(2)
1
```

```
>>> range(-10,10).index(2)
12
```
```
  __contains__(self, key, /)
      Return key in self.
```

上述self key /的意义是？



```
>>> range(-10,10).__contains__(3)
True
```

```
>>> range(-10,10).__eq__(3)
NotImplemented
>>> range(-10,10).__eq__(range(-10,10))
True
>>> range(-10,10).__eq__(range(-11,10))
False
```


>>> range(-10,10).__getitem__(3)
-7
















