# random模組的使用
```
本課程主要分享Python內建的random模組的使用

Python內建的模組==只要使用 import 載入即可,無須安裝
```
```
參考資料
https://docs.python.org/3/library/random.html
```
# 內容主題
```
[1]載入方式: 
[2]常用函數
[3]龍大大 我的億 大樂透 開獎中心
```
### [1]載入方式: 
```
import random
from random import *
import random as rand
```
### [2]常用函數
```
(1)Functions for integers:產生 整數 的隨機亂數函式
   random.randrange()
   random.randint(a, b)  返回隨機整數 N 滿足 a <= N <= b。相當於 randrange(a, b+1)
   
(2)Functions for sequences::產生 序列資料 的隨機亂數函式
   random.choice()
   random.shuffle()
   random.sample()
   
(3)Real-valued distributions產生 浮點數(實數)[滿足某種機率分布] 的隨機亂數函式
   random.random()
   random.uniform(a, b)   
   
   [滿足某種機率分布] 的隨機亂數函式
   random.betavariate(alpha, beta)==Beta distribution
   random.gauss(mu, sigma)==Gaussian distribution
```
```
random.randrange(stop)
random.randrange(start, stop[, step])
從 range(start, stop, step) 返回一個隨機選擇的元素。 這相當於 choice(range(start, stop, step))
```
```
程式實作:https://github.com/python/cpython/blob/3.8/Lib/random.py
第244-248行

    def randint(self, a, b):
        """Return random integer in range [a, b], including both end points.
        """

        return self.randrange(a, b+1)
```
### (2)Functions for sequences::產生 序列資料 的隨機亂數函式
```
random.choice(seq):從非空序列 seq 返回 一個 隨機元素。 如果 seq 為空，則引發 IndexError。
random.sample(population, k):返回從總體序列或集合中選擇的唯一元素的 k 長度清單。 用於無重複的隨機抽樣。

random.shuffle(x[, random]):將序列 x 隨機打亂位置
```
```
程式範例
https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/357241/
https://dotblogs.com.tw/chris0920/2010/10/25/18560
```
```
import random

num = [1, 2, 3, 4, 5]
sli = random.sample(num, 3)

print(num)
print(sli)
```
### [3]龍大大 我的億 大樂透 開獎中心
```
說明底下程式的處理邏輯
```
```
import random as rand

list1 = rand.sample(range(1,50), 7)

special = list1.pop()

list1.sort()

print("龍大大 我的億 大樂透 開獎中心")
print("本期大樂透中獎號碼為：", end="")
for i in range(0,6):
    if i == 5:    print(str(list1[i]))
    else:    print(str(list1[i]), end=", ")
print("本期大樂透特別號為：" + str(special))
```
```
說明底下程式的處理邏輯

[1]產生從1到49的7個不重複的整數

[2]設定中獎號法
挑出一個當作 特別號
剩下六個當作 中獎號碼

[3]印出 特殊格式輸出 的 中獎單
```
