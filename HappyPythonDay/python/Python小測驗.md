# 程式閱讀題
```
1.print("3*2*(17-2)")會印出甚麼結果:
(A)0   (B)90  (C)出現錯誤,無法印出  (D)3*2*(17-2)

2.print(3*2*(17-2))會印出甚麼結果:
(A)0   (B)90  (C)出現錯誤,無法印出  (D)3*2*(17-2)

3.print("abc""+""def")會印出甚麼結果:
(A)出現錯誤,無法印出   (B)abc+def  (C)abc""+""def  (D)abcdef

4.print("abc"+"def")會印出甚麼結果:
(A)出現錯誤,無法印出   (B)abc+def  (C)abc""+""def  (D)abcdef

5.底下程式執行後結果為何?
word = "arttarataaa"
print(word.replace("a", "z",3))
(A)出現錯誤,無法印出   (B)arttarataaa  (C)zrttzrztaaa (D)zrttzrztzzz

6.底下程式執行後結果為何?
word = "arttarataaa"
print(word.replace("a", "z"))
(A)出現錯誤,無法印出   (B)arttarataaa  (C)zrttzrztaaa (D)zrttzrztzzz

7根據底下程式,下列敘述何者為非?[複選題]

names = ['龍', '聖']
index = 0

while index < len(names):
    name = names[index]
    print(name)
    index = index + 1
    
(A)len(names)=2  
(B)names[1]是 龍 
(C)程式執行完後,index最後為2
(D)如果把條件改成 index > len(names),中index最後為2
```
# 程式設計題
```
for 迴圈(loop)的技巧
1.使用for 迴圈(loop)計算1+2+3+.....100
2.使用for 迴圈(loop)計算1+3+5+7.....+99
3.使用for 迴圈(loop)計算1*3*5*7.....*99

while 迴圈(loop)的技巧
4.使用while 迴圈(loop)計算1+2+3+.....100
5.使用while 迴圈(loop)計算1+3+5+7.....+99
6.使用while 迴圈(loop計算1*3*5*7.....*99
```


# 程式設計題解答(有各種寫法,找寫最快的分數最高)

### 使用for 迴圈(loop)計算1+2+3+.....100
```
sum=0

for x in range(1,101):
  sum +=x
  
print(sum)
```
### 使用for 迴圈(loop)計算1+3+5+7.....+99
```
sum=0

for x in range(1,101,2):
  sum +=x
  
print(sum)
```
### 使用for 迴圈(loop)計算
```
1*3*5*7.....*99
```
```
total=1

for x in range(1,101,2):
  total *=x
  
print(total)
```

### 使用while 迴圈(loop)計算1+2+3+.....100
```
sum = 0
x=1

while x < 101:
  sum +=x
  x = x+1
  # x += 1
  
print(sum)
```
### 使用while 迴圈(loop)計算1+3+5+7.....+99
```
sum = 0
x=1

while x < 101:
  sum +=x
  x = x+2
  # x += 1
  
print(sum)
```

### 使用while 迴圈(loop)計算
```
1*3*5*7.....*99
```
```
total = 1
x=1

while x < 101:
  total *=x
  x = x+2     # x += 2
  
print(total)
```
