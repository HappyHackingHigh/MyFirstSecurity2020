# 眾多資料型態(data Type)及其各種運算
    >* 數值(Numeric)資料及其運算
    >* 字串(string)及其運算
    >* 列表(list)資料及其運算
    >* 字典(dict)資料及其運算  
    >*[自我練習]tuple資料及其運算  
    >*[自我練習]set資料及其運算 
 ```
 本課程規劃讓同學快速掌握python程式的開發技術
 還有更多技術及細節 請務必閱讀更多教材深入
 ```
### 快速入門 
```
數值(Numeric)資料及其運算

a = 17 / 3
b = 17 // 3
c = 17 % 3

a,b,c
```
```
字串(string)及其運算

var1 = 'Hello Python!'
 
print("var1[0]: ", var1[0])
print("var1[1:8]: ", var1[1:8])

變數值以一對雙引號 (「"」)或單引號 (「'」)
存取字串中的值: 使用方括號
```
```
列表(list)資料及其運算


list1 = [21, 33, 14, 12, 32,98]

list1[1]
len(list1)
max(list1)
min(list1)
sum(list1)

list是Python中最基本的資料結構。
創建一個list，只要把逗號分隔的不同的資料項目使用方括號括起來即可
list中的每個元素都分配一個數字(位置|索引)，第一個索引是0，第二個索引是1，依此類推。
list都可以進行的操作包括索引，切片，加，乘，檢查成員。
Python已經內置確定list的長度以及確定最大和最小的元素的方法。
```
```
字典(dict)資料及其運算 
 
dict = {'Name': 'DaDaLong', 'Age': 17, 'Class': 'First'}
 
print("dict['Name']: ", dict['Name'])
print("dict['Age']: ", dict['Age'])

字典的每個鍵值(key=>value)對  用冒號(:)分割，
每個對之間用逗號(,)分割，
整個字典包括在花括弧({})

d = {key1 : value1, key2 : value2 }

鍵必須是唯一的，但值則不必。

值可以取任何資料類型，
但鍵必須是不可變的，如字串，數位或元組。
```
```
資料型態( Data Type)學習重點:
各種運算
各種內建函數
型態轉換
運算優先順序
```
# 數值(Numeric)資料及其運算
```
Python 支持三種不同的數值型別(Data Type)：
[1]Int 整數，是可以是正或負整數，不帶小數點。
  Python3  int是沒有限制大小的，可以當作 Long 類型使用，所以 Python3 沒有 Python2 的 Long 類型。
[2]浮點數(float) :由整數部分與小數部分組成，浮點型也可以使用科學計數法表示（2.5e2 = 2.5 x 10 0 = 250）
[3]複數( (complex)) - 複數由實數部分和虛數部分構成，可以用a + bj,或者complex(a,b)表示， 複數的實部a和虛部b都是浮點型。

https://www.w3schools.com/python/python_exercises.asp
```


# 數值型別(Numerics Data Type)的各種運算:

```
算術運算子
比較（關係）運算子
賦值運算子
邏輯運算符
位元運算子
成員運算子
身份運算子
```
```
底下以範例快速示範,同學請勤作練習,完成你自己的python學習之路
https://www.w3schools.com/python/python_operators.asp
```

# 算術運算
```
-3%2
```

```
a = 7//2
b = 7.0//2
c = 7//2.0

a,b,c
```
```
5 ** 2
```
### Logical Operators::
```
x = 5

print(x > 3 and x < 10)
```
```
x = 5

print(x > 3 or x < 4)
```
```
x = 5

print(not(x > 3 and x < 10))
```
## Bitwise Operators
```
#!/usr/bin/python3
 
a = 60            # 60 = 0011 1100 
b = 13            # 13 = 0000 1101 
c = 0

print ("0 - a =  60 = 0011 1100(二進位) ")
print ("0 - b =  13 = 0000 1101(二進位) ")
c = a & b;        # 12 = 0000 1100
print ("1 - c = a & b的值為：", c)
 
c = a | b;        # 61 = 0011 1101 
print ("2 - c = a | b的值為：", c)
 
c = a ^ b;        # 49 = 0011 0001
print ("3 - c= a ^ b 的值為：", c)
 
c = ~a;           # -61 = 1100 0011
print ("4 - c = ~a的值為：", c)
 
c = a << 2;       # 240 = 1111 0000
print ("5 - c = a << 2的值為：", c)
 
c = a >> 2;       # 15 = 0000 1111
print ("6 - c = a >> 2的值為：", c)

```

## 各種數學函數
```
https://www.w3schools.com/python/python_ref_functions.asp
```
### 作業:完成十種函數的自我測試報告

## 進位轉換
```
x = bin(36)
x

x = oct(36)
x

x = hex(255)
x

```
## int()函數的測試
```
https://www.w3schools.com/python/ref_func_int.asp
```
```
x=int('10',2)
x

x=int('10',16)
x

x=int('10',8)
x
```
## round()函數的測試
```
#Round a number to only two decimals:

x = round(5.76543, 2)
print(x)

# Round to the nearest integer:

x = round(5.76543)
print(x)

```
## Python 類型轉換
```
有時候，我們需要對資料內置的類型進行轉換，
資料類型的轉換只需要將資料類型作為函數名即可。


int(x) 將x轉換為一個整數。
float(x) 將x轉換到一個浮點數。
complex(x) 將x轉換到一個複數，實數部分為 x，虛數部分為 0。
complex(x, y) 將 x 和 y 轉換到一個複數，實數部分為 x，虛數部分為 y。x 和 y 是數字運算式。
```

```
a = 1.0004
int(a)

b = 0.9999
int(a)
```

## 運算子優先順序

### picoCTF 2017 : compute-rsa-50
```
RSA encryption/decryption is based on a formula that anyone can find and use, 
as long as they know the values to plug in. 
Given the encrypted number 150815, d = 1941, and N = 435979, what is the decrypted number?

HINTS

decrypted = (encrypted) ^ d mod N
```

# 字串(string)及其運算

# 列表(list)資料及其運算

# 字典(dict)資料及其運算 
