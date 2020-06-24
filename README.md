# MyFirstSecurity2020
```
高中職生資安培訓

官方臉書:高中職生資安研習營
```
# 上課手則
```
[1]上課期間須專注學習

[2]上課期間不得有{玩手機|打電動|呼呼大睡}等違反規範的行為,
若有此行為將被請出, 且不發放證書。
```
# 課程學習地圖


# 體驗營

### 體驗營相關學習資源:CTF==Capture the flag搶旗大賽
```
[1]初體驗隱寫術

[2]資安倫理

[3]網站安全

[4]編碼與解碼

[5]加密與解密

[6]網路封包分析

如果還有時間... ...
[7]Linux初體驗

```
# Happy Python Day
```
早上三小時:快速掌握python程式技術
```
```
早上自主練習:
[1]玩成底下小小測驗:
[2]完成底下程式小測驗 
[3]有空,完成底下難題測驗
還有力氣嗎?
```
```
下午三小時:使用python解CTF搶旗大賽題目
[1]使用python解編碼與解碼問題
[2]使用python解古典密碼破密問題
[3](*時間充裕才會教)使用python解PPC問題
    特別要掌握pwntools技術[PWN必備技術]
```
## 程式閱讀題
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
## 程式設計題
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

# Happy Linux Day
```
宗旨:熟悉linux作業系統及重要基礎指令[搶旗大賽基礎篇]
     奠定後續深入課程基礎
     
[1]熟悉linux作業系統及重要基礎指令
[2]使用linux解隱寫術問題
[3]熟悉linux上C/C++程式開發與逆向分析

早上3小時
[1]熟悉linux作業系統及重要基礎指令
[2]使用linux解隱寫術問題

下午3小時
[3]熟悉linux上C/C++程式開發與逆向分析
3.1.程式開發
使用gcc開發c程式技術
使用g++開發c++程式技術

3.2.
執行檔分析
程式執行追蹤與分析技術

3.3.逆向分析
將執行檔逆向成組合程式
使用objdump將執行檔逆向成Intel組合程式
使用objdump將執行檔逆向成AT&T組合程式
gdb實戰與案例分析

3.4.c漏洞程式分析體驗
一支超簡單有buffer overflow漏洞的C程式
編譯技術(1)直接編譯成漏洞的執行檔
編譯技術(2)編譯成具有安全保護的執行檔
分析與測試有漏洞的執行檔
撰寫攻擊漏動的python程式
攻擊成功的權限取得
```
### Linux學習
```
熟悉底下linux指令:
```
```
完成小小的測驗練習:
```
```
進階實戰學習:完成底下網址的線上練習
https://overthewire.org/wargames/bandit/
```
# MyFirstSecurity summer camp
```
北、中、南同時舉辦
```
## Crypto：
```

上午課程：

下午課程：

學員先修技能：
```
## Reverse：
```
學習如何使用靜態及動態除錯工具分析程式執行行為，以及閱讀組合語言程式之能力
介紹基本逆向工程及動態分析工具（objdump strace/ltrace gdb）

上午課程：

下午課程：

學員先修技能：Linux基礎指令操作
```
## Web
```

上午課程：

下午課程：

學員先修技能：
```
## Pwn
```
學習基本程式漏洞與攻擊技巧
包含:ELF 保護機制、Buffer Overflow 漏洞介紹與攻擊技術分析

上午課程：

下午課程：

學員先修技能：
[1]基礎逆向技巧
[2]能看懂組合語言
[3]Linux基本指令
```
# 破了許多關卡,解了許多大賽題目,接著呢??
```
請將你的佐證資料備妥,申請加入

台灣好厲駭:高階資安培訓

故事才開始....Security4yourlife
```
```
2020年度申請即將展開,敬請期待.......
```
```
CTF培訓主題:
[1]GHIDRA逆向分析實戰
[2]Symbolic execution逆向分析實戰
[3]angr|Z3 逆向分析實戰
[4]heap exploitation
.....族繁不及備載,請積極參加 
.....限定版課程
```
