# Python與古典破密
```
依時間規範講解底下題目,特別是強調處理邏輯與程式語法
[1]使用Python求解變形caesar密碼 RC3 CTF 2016 : salad-100
[2]AlexCTF: Fore1: Hit the core
[3]School CTF 2015: affine-cipher-100(教)

謝謝教授
繼續努力
20200804
```
## Crypto 101:RC3 CTF 2016 : salad-100
```
import string

caesaralpha = "abcdefghijklmnopqrstuvwxyz0123456789"

def caesar(input_string,rot) :
    output_string = ""
    for i in range(len(input_string)):
        if input_string[i].isalnum():
            idx = (caesaralpha.find(input_string[i]) + rot) % len(caesaralpha)
            output_string += caesaralpha[idx]
        else:
            output_string += input_string[i]
    return output_string

enc = '7sj-ighm-742q3w4t' # encrypt data

for i in range(len(caesaralpha)):
    print(caesar(enc, i))
```

```
'rc3-2016-romangod'.upper()
```

# AlexCTF: Fore1: Hit the core
```
https://github.com/ctfs/write-ups-2017/tree/master/alexctf-2017/forensics/fore1-hit-the-core-50

本題必須使用 linux strings 指令照出關鍵字
strings 指令==在目的檔或二進位檔案中查找可列印的字串
strings - print the strings of printable characters in files


底下是AlexCTF 2017改編的題目

你能解出古典密碼的答案嗎?

cvqAeqacLtqazEigwiXobxrCrtuiTzahfFreqc{bnjrKwgk83kgd43j85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}
解答格式:ALEXCTF{XXXXXXXXXXXXXXXXXXXXXXXXXXX}
```
#### 第一種解法
```
cipher='cvqAeqacLtqazEigwiXobxrCrtuiTzahfFreqc{bnjrKwgk83kgd43j85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}'

cipher=cipher[3:] 

flag = '' 

for x in range(0,len(cipher),1): 
    if x%5==0: 
       flag +=cipher[x]
        
print(flag)
```
#### 第二種解法
```

s = 'cvqAeqacLtqazEigwiXobxrCrtuiTzahfFreqc{bnjrKwgk83kgd43j85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}' 
print(s[3::5])
```
#### 第三種解法
```
cipher='cvqAeqacLtqazEigwiXobxrCrtuiTzahfFreqc{bnjrKwgk83kgd43j85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}' 

''.join(cipher[3 : : 5])
```

# Crypto 102::School CTF 2015: affine-cipher-100(教)
```
import string 

# 先產生小寫字母,再加入其他
s = string.ascii_lowercase # a-z 
s += '_'

# 使用 字典(dictionary)資料型態 來建立 轉換表|解密規則
d = {} 

for c in range(len(s)): 
      d[s[(c*4 + 15)%27]] = s[c] 

# 使用 轉換表|解密規則 逐字解出答案
ciphertext = 'ifpmluglesecdlqp_rclfrseljpkq' 
s1 = '' 

for x in ciphertext : 
     s1 += d[x] 

# 印出答案
print(s1)
```





