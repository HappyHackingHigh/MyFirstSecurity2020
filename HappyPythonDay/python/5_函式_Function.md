# 函式的定義:

```
函數代碼塊以 def 關鍵字開頭，後接函數識別字名稱和圓括號()。
任何傳入參數和引數必須放在圓括號中間。圓括號之間可以用於定義參數。
函數的第一行語句可以選擇性地使用文檔字串—用於存放函數說明。
函數內容以冒號起始，並且縮排。
return [運算式] 結束函數，選擇性地返回一個值給調用方。不帶運算式的return相當於返回 None。
函式包含標頭和主體。
標頭(header)起源於def關鍵字，後接函式名稱和參數，最後以冒號結尾。
```
```
def sum(i1, i2):
    result = 0
    for i in range(i1, i2):
        result += i
    return result

def main():
    print("Sum from 1 to 10 is", sum(1, 11)) 
    print("Sum from 20 to 37 is", sum(20, 38))
    print("Sum from 35 to 49 is", sum(35, 50))

main() # Call the main function
```
## 【Python 練習實例47】練習撰寫swap(a,b)函式
```
寫一個函式將輸入的兩個變數值互換
```
```

#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
def swap(a,b):
    a,b = b,a
    return (a,b)
 
if __name__ == '__main__':
    x = 10
    y = 20
    print('x = %d,y = %d' % (x,y))
    x,y = swap(x,y)
    print('x = %d,y = %d' % (x,y))
```
# 函式與回傳值
```
Python的函式是否有無回傳值，端視函式是否有無return敘述。

若函式沒有回傳值，預設是回傳一None特殊值。
因此，沒有回傳值的函式也稱為None函式。
None值可以指定給一變數，表示此變數沒有參考到任何的物件
```

## Python的函數可以回傳多個值(超棒der)
```
#!/usr/bin/python 
# -*- coding: UTF-8 -*- 

def sort(number1, number2):
    if number1 < number2:
        return number1, number2
    else:
        return number2, number1

num1, num2 = sort(31, 25)

print("num1 is", num1)
print("num2 is", num2)
```
### [作業]:def sort(number1, number2, number3):

# 函式與參數

```
Default arguments預設參數
Positional arguments位置參數
Keyword arguments關鍵字參數
```

### **arguments參數**的使用技巧
```
#!/usr/bin/python 
# -*- coding: UTF-8 -*- 

def printArea(width = 11, height = 12):
    area = width * height
    print("width:", width, "\theight:", height, "\tarea:", area)

printArea() 
printArea(4, 2.5) # Positional arguments width = 4 and height = 2.5
printArea(height = 5, width = 3) # Keyword arguments width 
printArea(width = 1.2) # Default height = 2
printArea(height = 6.2) # Default widht = 1
```

### [小小測驗]:執行下列程式並說明其結果"""
```
#!/usr/bin/python 
# -*- coding: UTF-8 -*- 

def hello_3(greeting='Hello', name='world'): 
    print('{}, {}!'.format(greeting, name)) 

    
hello_3() 
hello_3('Greetings') 
hello_3('Greetings', 'universe')
hello_3(name='GGGGGGoood')
```
### [特別注意]要將字典dict型的資料傳給函數時,記得要使用**"""
```
params = {'name': 'Sir Simon Rattle', 'greeting': 'To my Great Conductor'}
hello_3(**params)
```

## collectiong parameters(任意數量的參數):* 與 **
```
如何撰寫擁有任意數量參數的函式:
```
```
def print_params(*params): 
    print(params) 

print_params('Testing') 

print_params(1, 2, 3) 


# return的是tuple資料型態

#可和一般參數齊用

def print_params_2(title, *params): 
    print(title) 
    print(params)

print_params_2('Params:', 1, 2, 3)
print_params_2('Nothing:')
```
### 撰寫擁有任意數量參數的函式且要支援關鍵字參數==>使用**
```
def print_params_3(**params): 
    print(params) 

print_params_3(x=1, y=2, z=3) 

# return的是dict(字典資料型態)

def print_params_4(x, y, z=3, *pospar, **keypar): 
    print(x, y, z) 
    print(pospar) 
    print(keypar) 

print_params_4(1, 2, 4, 5, 6, 7, foo=1, bar=2)

print_params_4(1, 2)

```
# 變數的有效範圍
```
變數的有效範圍(Scope)：變數在程式可參考的範圍。

區域變數(local variable):宣告在函式內部的變數

全域變數(global variables):宣告在所有函式外部的變數
```
```
x = 111

def f1():
    x = 222
    print(x) 

f1()
print(x)

x = 1

def increase():
    global x
    x =  x + 1
    print(x) 

increase()
print(x)
increase()
increase()
print(x)
```

# 遞迴函式 ==> recursive vs iterative(loop)

```
[程式開發作業]費氏數列
[程式開發作業]1+2+3+....+n
[程式開發作業]n!
[程式開發作業]x的n次方
[程式開發作業]二項係數
[程式開發作業][Ackermann函式](https://en.wikipedia.org/wiki/Ackermann_function)
[程式開發作業]河內塔
[程式開發作業]八皇后問題
[程式開發作業]binary search二元搜尋法
```

## 費氏數列

```
費氏數列Fibonacci sequence又稱黃金分割數列
0、1、1、2、3、5、8、13、21、34、……。

在數學上，費波那契數列是以遞迴的方法來定義：
F(0) = 0    (n=0)
F(1) = 1    (n=1)
F(n) = F(n-1)+ F(n-2)(n=>2)
```

#### 方法一:使用 recursive
```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

def fib(n):
    if n==1 or n==2:
        return 1
    return fib(n-1)+fib(n-2)

print(fib(10))
```
#### 方法二:使用 iterative
```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
def fib(n):
    a,b = 1,1
    for i in range(n-1):
        a,b = b,a+b
    return a
 
print(fib(10))
```

###【Python 練習實例28】

```
有5個人坐在一起，
問第五個人多少歲？他說比第4個人大2歲。
問第4個人歲數，他說比第3個人大2歲。
問第三個人，又說比第2人大兩歲。
問第2個人，說比第一個人大兩歲。
最後問第一個人，他說是10歲。
請問第五個人多大？
```

###  問題:要如何知道函數被呼叫的次數??
```
遞迴函式的呼叫次數==>全域變數的應用


#!/usr/bin/python
# -*- coding: UTF-8 -*-

def fib(x):	
	global numFibCalls
	numFibCalls += 1
	
	if x == 0 or x == 1:
           return 1
	else:
          return fib(x-1) + fib(x-2)

def testFib(n):
	for i in range(n+1):
          global numFibCalls
          numFibCalls = 0
          print('fib of', i, '=', fib(i))
          print('fib called', numFibCalls, 'times.')

testFib(4)

```

# Python內建函數==>Built-in Functions:

```
https://docs.python.org/2/library/functions.html
https://www.programiz.com/python-programming/methods/built-in
```

### hex(x):Convert an integer number to a lowercase hexadecimal string prefixed with "0x"
```

hex(255)

hex(-42)

```
### oct(x):Convert an integer number to an octal string prefixed with "0o"
```
oct(8)

oct(-56)

```
### bin(x):Convert an integer number to a binary string prefixed with "0b"
```
bin(3)

bin(-10)
```
