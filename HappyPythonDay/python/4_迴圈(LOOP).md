
# Python Loops

課程目標：
```
1.使用range 函式 的功能建立整數循序數列

2.使用for 廻圈 執行固定次數的廻圈運算(通常)
3.使用while 廻圈執行沒有固定次數的廻圈運算

4.continue 指令 
是在廻圈執行中途暫時停住不往下執行，而跳到廻圈的起始處執行

5.break 指令:可在廻圈執行中途強迫跳離廻圈，跳到廻圈後面的程式繼續執行。

6.廻圈中又包含廻圈的巢狀廻圈　設計九九乘法表
```

```
PS:Python沒有do… while 廻圈===>你自己實作一個吧?!!
```
# range() 函式
```
使用range 函式 的建立整數循序數列
list1=range(10)
print(list1)

print(list(list1))

list1=range(-4,5)
print(list(list1))

for x in range(19):
  print(x)

for x in range(0,19,2):
  print(x)

for x in range(20,11,-1):
  print(x)

for x in range(0,19,-1):
  print(x)

output = ''

for x in range(0,19,3):
  output += str(x)
  print(output, end=" ")

output = ''

for x in range(0,19,3):
  print(x, end=" ")

list1 = range(0,19,3)

for x in list1:
  print(x, end=" ")
```

# for 廻圈 
```
使用for 廻圈 執行固定次數的廻圈運算(通常)


for n in range(5):
  print(n)

for n in range(10):
    print(n, end='@')

    #print(n, end='%%%%')

mysum = 0

for n in range(5):
  mysum += n
  print(mysum)

mysum = 0

for n in range(5):
  mysum += n

print(mysum)

x = int(input("請輸入一個正整數:"))
mysum = 0

for n in range(x):
  mysum += n

print(mysum)
```
### [程式閱讀題]執行下列程式並說明其結果
```
如果第五行改成  if (number % 2 = 0):

答案又會是甚麼??

numbers = [21, 4, 35, 1, 8, 7, 3, 6, 9]
my_numbers = []

for number in numbers:
  if (number % 2 != 0): 
    my_numbers.append(number)

print(my_numbers)
```

### [程式閱讀題] 執行下列程式並說明其結果
```
總和是多少?


#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
for i in range(1,6):
    for j in range(1,5):
        for k in range(1,7):
            if( i != k ) and (i != j) and (j != k):
                print(i,j,k)
```

### [程式閱讀題] 下列程式輸入淨利潤為11111時請問輸出為何?"""
```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
i = int(input('淨利潤:'))

arr = [1000000,600000,400000,200000,100000,0]
rat = [0.01,0.015,0.03,0.05,0.075,0.1]
r = 0

for idx in range(0,6):
    if i>arr[idx]:
        r+=(i-arr[idx])*rat[idx]
        print((i-arr[idx])*rat[idx])
        i=arr[idx]

print(r)
```
# While Loop

### n階程的計算:n!=1*2*3*⋯*n
```
1!　=　１
2!　=　1*2　=　2
3!　=　1*2*3　=　6
```

輸入::一個正整數 n

輸出::

```
當使用者輸入一個正整數 n 後，程式就會顯示
1*2*3*...*n 的乘積
```

請使用 while loop設計這個程式
```
total = i = 1

n = int(input("請輸入正整數 n 的值："))

while(i<=n):
    total *= i  
    i+=1      

print("%d!=%d" % (n, total))

```
# break 指令
```
可在廻圈執行中途強迫跳離廻圈，跳到廻圈後面的程式繼續執行。

fruits = ["香蕉","蘋果","橘子","鳳梨","西瓜"]

while True:
    fruit = input("請輸入喜歡的水果(Enter 結束)：")

  #  if (fruit==""):
  #      break

    n = fruits.count(fruit) 
    if (n>0):  # 串列元素存在
        p=fruits.index(fruit)
        print("%s 在串列中的第 %d 項" %(fruit,p+1))
    else:
        print(fruit,"不在串列中!")
```
# continue 指令 
```
在廻圈執行中途暫時停住不往下執行，而跳到廻圈的起始處繼續執行


n = int(input("請輸入正整數："))

for i in range(1, n+1):
    if i % 5 ==0:
        continue
    print(i,end=" ")
```

# 巢狀廻圈Nested Loop
```
廻圈中又包含廻圈的巢狀廻圈　

留給你當作業：九九乘法表
```
