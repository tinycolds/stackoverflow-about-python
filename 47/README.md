| rank | ▲ | ✰ | vote | url |
|:-:|:-:|:-:|:-:|:-:|
|  47  | 435 | 86 | 477 | [url](http://stackoverflow.com/questions/1602934/check-if-a-given-key-already-exists-in-a-dictionary) |

***

## 检查一个键在字典中是否存在

在更新字典之前想检查键是否存在.我写了如下代码:

```python
if 'key1' in dict.keys():
  print "blah"
else:
  print "boo"
```

我想这不是最好的方法,还有什么更好的方法?

***

用`in`.

```python
d = dict()

for i in xrange(100):
    key = i % 10
    if key in d:
        d[key] += 1
    else:
        d[key] = 1
```

如果你想要一个默认值,你可以用`dict.get()`:

```python
d = dict()

for i in xrange(100):
    key = i % 10
    d[key] = d.get(key, 0) + 1
```

如果相对所有值设置默认值可以用`collections`模块的`defaultdict`函数:

```python
from collections import defaultdict

d = defaultdict(lambda: 0)

for i in xrange(100):
    d[i % 10] += 1
```

但是总而言之`in`是最好的方法.
