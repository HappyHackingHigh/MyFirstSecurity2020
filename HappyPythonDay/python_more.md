#
```
# -*- coding: utf-8 -*-
```
# CTF解題
```
https://0x90r00t.com/
```
# Python Docstring
```



https://stackoverflow.com/questions/3898572/what-is-the-standard-python-docstring-format


Google Style Python Docstrings

https://www.sphinx-doc.org/en/master/usage/extensions/example_google.html#example-google


'''
This is an example of Google style.

Args:
    param1: This is the first param.
    param2: This is a second param.

Returns:
    This is a description of what is returned.

Raises:
    KeyError: Raises an exception.
'''
"""

def demo():
    """函數的文件字串"""
    pass
    
print(demo.__doc__)

def swap(a,b):
    """
    swap(a,b)功能是.................
    """ 
    a,b = b,a
    return (a,b)

print(swap(3,5))
print(swap.__doc__)

```

```
## 匿名函數==>lambda 運算式
```
匿名函數==沒有函數名稱、臨時使用的小函數
使用lambda 運算式來宣告匿名函數
lambda 運算式只能包含一個運算式， 不允許複雜的語句，但運算式中可呼叫其他函數
```

# 把lambda運算式當做函數

f1 = lambda x, y, z: x+2*y+3*z
print(f1(2,3,1))

#在lambda 運算式中呼叫其他函式(重要技術)
def myfunc(m):
    return m*m

my_list = [1, 3, 5, 7, 9]

#使用python的map()
map(lambda x:myfunc(x), my_list)
```
