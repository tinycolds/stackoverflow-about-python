| rank | ▲ | ✰ | vote | url |
|:-:|:-:|:-:|:-:|:-:|
|  56 | 390 | 59 | 554 | [url](http://stackoverflow.com/questions/510972/getting-the-class-name-of-an-instance-in-python) |

***

## 如何获取实例的类名

如何才能获取一个实例对象的类名?

我想或许[the inspect module](https://docs.python.org/library/inspect)可以实现,但是好像还没有发现什么能帮我的.或许可以分析`__class__`成员,但是我不知道怎么用.

***

你试没试类里的`__name__`属性?比如`x.__class__.__name__`或许可以得到你想要的

```python
>>> import itertools
>>> x = itertools.count(0)
>>> x.__class__.__name__
'count'
```

注:如果你用的是新式类(从Python2.2),你可以调用`type()`函数来替代:

```python
>>> type(x).__name__
'count'
```

像`int`这种内建方法也可以:

```python
>>> (5).__class__.__name__
'int'
>>> type(5).__name__
'int'
```
