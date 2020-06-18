# Python實戰 CTF::使用Python編碼與解碼
```
學習目標:
[1]使用Python程式與內建函數進行ASCII的編碼與解碼
[2]使用Python標準函式庫(Base 64模組)進行BASE64的編碼與解碼
```
# 編碼與解碼101

## 使用Python程式與內建函數進行ASCII的編碼與解碼

### Python 內建函數(Built in Functions):chr()與ord()
```
https://docs.python.org/3/library/functions.html

chr(97)

chr(66)

#ord('a')
#print(bin(ord('a')))
#oct(ord('a'))
print(hex(ord('a')))
```
### 編碼與解碼 101---ASCII編碼解題

### 字串的分割
```
a="66 114".split("")
a

a="66 114".split("  ")
a

a="66 114".split(" ")
a
type(a)
```
### 把每一個分割後的字串==轉成整數後===再編碼出ASCII的字
```
a="66 114".split(" ")

result=''

for x in a:
  y=chr(int(x))
  result += y
# result = result + y 

result
```
### 最後的解答
```
#!/usr/bin/python

c = '66 114 101 97 107 65 76 76 67 84 70 123 65 109 118 48 117 68 121 101 114 118 80 116 109 86 114 57 83 83 83 75 125'

flag = ""

for _ in c.split(' '):
  flag += chr(int(_))

print(flag)
```
#### 
```
#!/usr/bin/python

c = '66 114 101 97 107 65 76 76 67 84 70 123 65 109 118 48 117 68 121 101 114 118 80 116 109 86 114 57 83 83 83 75 125'

flag = ""

for x in c.split(' '):
  flag += chr(int(x))

print(flag)
```

## 使用Python標準函式庫進行BASE64的編碼與解碼

###  Python 標準函式庫 (Standard Library)
```
C++ 有強大的標準模板庫(Standard Template Library，STL）

Python也有強大的標準函式庫 (Standard Library)

本課程示範幾個範例,帶你認識Python 標準函式庫

推薦書籍與資源

[1]官方說明
英文 https://docs.python.org/3/library/
中文 https://docs.python.org/zh-tw/3/library/index.html

[2]厚達上千頁的範例示範說明書

The Python 3 Standard Library By Example
Doug Hellmann

https://pymotw.com/3/
https://bitbucket.org/dhellmann/pymotw-3/src/master/
```

## Python 標準函式庫的Base 64 模組
```
What does the 'b' character do in front of a string literal?

https://stackoverflow.com/questions/6269765/what-does-the-b-character-do-in-front-of-a-string-literal
```
### 使用Base 64 模組編碼:b64encode()
```
import base64

data =b'BreakAllCTF{HappyPythonDay}'
encoded_data = base64.b64encode(data)
print('Original Data :', data)
print('Encoded :', encoded_data)
```
### 使用Base 64 模組解碼:b64decode()
```
import base64

encoded_data = b'QnJlYWtBTExDVEZ7NTN1c1pRM2hXVzI1ZGNoWjdkWGV9'
decoded_data = base64.b64decode(encoded_data)
print('Encoded :', encoded_data)
print('Decoded :', decoded_data)
```
### 使用Base 64 模組也可以進行Base 32編碼與解碼
```
import base64

original_data = b'BreakAllCTF{HappyPythonDay}'
print('Original data:', original_data)

encoded_data = base64.b32encode(original_data)
print('Encoded :', encoded_data)

decoded_data = base64.b32decode(encoded_data)
print('Decoded :', decoded_data)
```
### [作業] 使用Pyhon程式解Crytpo 101: Base64及Base32哪兩題

# 編碼與解碼102

## angstromCTF 2016 : what-the-hex 20
```
Decode using hex and see what you get...
6236343a20615735305a584a755a58526659323975646d567963326c76626c3930623239736331397962324e72
```

### 先試看看[底下程式要在Python 2 才會正常執行]

步驟一:先將十六進位的數字轉成文字
```
'6236343a20615735305a584a755a58526659323975646d567963326c76626c3930623239736331397962324e72'.decode("hex")
```
```
'b64: aW50ZXJuZXRfY29udmVyc2lvbl90b29sc19yb2Nr'
```
步驟二:將獲得的文字再使用base 64解碼
```
import base64
base64.b64decode('aW50ZXJuZXRfY29udmVyc2lvbl90b29sc19yb2Nr')
```
### Python 3的寫法[使用 標準函式庫的binascii模組]
```
binascii模組包含很多用來方法來轉換二進位制和各種ASCII編碼的二進位制表示法
更多說明請參閱:
https://docs.python.org/zh-cn/3/library/binascii.html
```

步驟一:先將十六進位的數字轉成文字
```
import binascii
binascii.unhexlify('6236343a20615735305a584a755a58526659323975646d567963326c76626c3930623239736331397962324e72')
```
步驟二:將獲得的文字再使用base 64解碼
```
import base64
base64.b64decode('aW50ZXJuZXRfY29udmVyc2lvbl90b29sc19yb2Nr')
```

## 數字系統( number system)的轉換
```
10進位(Decimal)  二進位(binary)  八進位(Octal)  十六進位(Hexadecimal)

1011(二進位) = 13(八進位) = B(十六進位) = 11(十進位)

Python表示法:
0b1011(二進位:0b開頭)  0o13(八進位:0o開頭)   0xb(十六進位:0x開頭)
```

###  使用Python 內建函數(Built in Functions)解決  數字系統的轉換問題

```
https://www.w3schools.com/python/python_ref_functions.asp

bin()
oct()
int()
hex()
```
```
# 數字系統( number system)的轉換
# 使用Python程式將10進位(Decimal)數字轉換成二進位(binary), 八進位(Octal) 及 十六進位(Hexadecimal) 
# https://www.programiz.com/python-programming/examples/conversion-binary-octal-hexadecimal

bin_n = 0b1011

print("上述二進位數字可被轉換成:")
print(bin_n,"十進位(Decimal).")
print(oct(bin_n),"八進位(octal).")
print(hex(bin_n),"十六進位(hexadecimal).")
```
### 給你十進位的 344, 二進位(binary)|八進位(octal)|十六進位(hexadecimal)是多少?
```
dec = 344

print("10進位數字",dec,"可被轉換成:")
print(bin(dec),"二進位(binary).")
print(oct(dec),"八進位(octal).")
print(hex(dec),"十六進位(hexadecimal).")
```
## int[]內建函數
```
功能:將一個字串或數位轉換為整數型。

語法: int(x, base=10)

參數說明:
x -- 字串或數位。
base -- 進制數，預設是十進位。

返回值:會返回一個整數型資料。

```
### 底下程式執行結果為何?
```
# [參考資料]From https://www.programiz.com/python-programming/methods/built-in/int

# binary 0b or 0B
print("For 1010, int is:", int('1010', 2))
print("For 0b1010, int is:", int('0b1010', 2))

# octal 0o or 0O
print("For 12, int is:", int('12', 8))
print("For 0o12, int is:", int('0o12', 8))

# hexadecimal
print("For A, int is:", int('A', 16))
print("For 0xA, int is:", int('0xA', 16))
```

# Internetwache CTF 2016 : The hidden message
```
My friend really can’t remember passwords. So he uses some kind of obfuscation. Can you restore the plaintext?

Attachment: misc50.zip
```
把misc50.zip解壓縮後可以得到:
```
0000000 126 062 126 163 142 103 102 153 142 062 065 154 111 121 157 113
0000020 122 155 170 150 132 172 157 147 123 126 144 067 124 152 102 146
0000040 115 107 065 154 130 062 116 150 142 154 071 172 144 104 102 167
0000060 130 063 153 167 144 130 060 113 012
0000071
```

```
參考解答(writeups)
https://0x90r00t.com/2016/02/22/internetwache-ctf-2016-misc-50-the-hidden-message-write-up/
```
## 第一種解法:使用線上工具解

步驟一：線上工具
```
http://www.unit-conversion.info/texttools/octal/

V2VsbCBkb25lIQoKRmxhZzogSVd7TjBfMG5lX2Nhbl9zdDBwX3kwdX0K
```
步驟二：
```
import base64

encoded_data = b'V2VsbCBkb25lIQoKRmxhZzogSVd7TjBfMG5lX2Nhbl9zdDBwX3kwdX0K'
decoded_data = base64.b64decode(encoded_data)
print('Encoded :', encoded_data)
print('Decoded :', decoded_data)
```
## 第二種解法

### 先試看看是不是如你所想的一般.......
```
#!/usr/bin/python

c = '126 062 126 163 142 103 102 153 142 062 065 154 111 121 157 113 122 155 170 150 132 172 157 147 123 126 144 067 124 152 102 146 115 107 065 154 130 062 116 150 142 154 071 172 144 104 102 167 130 063 153 167 144 130 060 113 012'

flag = ""

for _ in c.split(' '):
  flag += chr(int(_,8))

print(flag)
```
## 接著就可以完成大業......
```
#!/usr/bin/python
import base64

c = '126 062 126 163 142 103 102 153 142 062 065 154 111 121 157 113 122 155 170 150 132 172 157 147 123 126 144 067 124 152 102 146 115 107 065 154 130 062 116 150 142 154 071 172 144 104 102 167 130 063 153 167 144 130 060 113 012'

flag = ""

for _ in c.split(' '):
  flag += chr(int(_,8))
  

solution = base64.b64decode(flag)
print(solution)
```
## SECCON CTF 2014: Easy Cipher 
```
87 101 108 1100011 0157 6d 0145 040 116 0157 100000 0164 104 1100101 32 0123 69 67 0103 1001111 1001110 040 062 060 49 064 100000 0157 110 6c 0151 1101110 101 040 0103 1010100 70 101110 0124 1101000 101 100000 1010011 1000101 67 0103 4f 4e 100000 105 1110011 040 116 1101000 0145 040 1100010 0151 103 103 0145 1110011 0164 100000 1101000 0141 99 6b 1100101 0162 32 0143 111 1101110 1110100 101 0163 0164 040 0151 0156 040 74 0141 1110000 1100001 0156 056 4f 0157 0160 115 44 040 0171 1101111 117 100000 1110111 0141 0156 1110100 32 0164 6f 32 6b 1101110 1101111 1110111 100000 0164 1101000 0145 040 0146 6c 97 1100111 2c 100000 0144 111 110 100111 116 100000 1111001 6f 117 63 0110 1100101 0162 0145 100000 1111001 111 117 100000 97 114 0145 46 1010011 0105 0103 67 79 1001110 123 87 110011 110001 67 110000 1001101 32 55 060 100000 110111 0110 110011 32 53 51 0103 0103 060 0116 040 5a 0117 73 0101 7d 1001000 0141 1110110 1100101 100000 102 0165 0156 33
```
```
[參考解答]
http://4ngelboy.blogspot.com/2014/12/span-display-block-overflow-hidden.html


很明顯的這段文字是由四種不同進位的數字所組成，必須判斷出他是屬於哪個進位在轉換成 ASCII code 印出，
不過起初在解的時候沒有發現有特別的規則，導致剛開始一直判別不出來，仔細觀察過後可發現每個進位的數字有不同的特徵：
2 進位：字串長度 >= 6
8 進位：開頭一定是 0
16 進位：必有英文字 6d
10 進位：上述之外的

https://github.com/S42X/CTF/blob/master/SECCON/EasyCipher.md
```
```

ord('a')

oct(10)

hex(10)

```
```
https://www.quora.com/How-do-I-convert-hex-into-a-string-using-Python

https://stackoverflow.com/questions/18806772/most-pythonic-way-to-convert-a-string-to-a-octal-number

http://mini-stable.blogspot.com/2015/03/python-int-hex-char-string.html
```
### Python - int, hex, char, string的轉換
```
Int to Hex:   hex(97)  # '0x61'
Int to Char:   chr(97)  # 'a'
Int to String:  str(97)  # '97'
Hex to int:  int('0x61', 16)  # 97
Hex to Char:   chr(int('0x61', 16)) # 'a'
Hex to String:
string = '61626364'
''.join(chr(int(string[i:i+2], 16)) for i in range(0, len(string), 2))  # 'abcd'
```
```
Char to Int: ord('a')  # 97
Char to Hex: hex(ord('a'))  # '0x61'
String to Int: int('97')  # 97
String to Hex:

string = 'abcd'
''.join([hex(ord(x))[2:] for x in string])  # '61626364'
```

```
string = '61626364'
''.join(chr(int(string[i:i+2], 16)) for i in range(0, len(string), 2))  # 'abcd'
```
### 使用python內建模組 binascii
```
https://docs.python.org/2/library/binascii.html
```
```
#coding:utf-8
import binascii
a = 'HappyCTF{Useful tools binascii}'
b = binascii.b2a_hex(a)
print b
print binascii.a2b_hex(b)
```

```
#!/usr/bin/python
import binascii

c = '87 101 108 1100011 0157 6d 0145 040 116 0157 100000 0164 104 1100101 32 0123 69 67 0103 1001111 \
     1001110 040 062 060 49 064 100000 0157 110 6c 0151 1101110 101 040 0103 1010100 70 101110 0124 \
     1101000 101 100000 1010011 1000101 67 0103 4f 4e 100000 105 1110011 040 116 1101000 0145 040 \
     1100010 0151 103 103 0145 1110011 0164 100000 1101000 0141 99 6b 1100101 0162 32 0143 111 1101110\
     1110100 101 0163 0164 040 0151 0156 040 74 0141 1110000 1100001 0156 056 4f 0157 0160 115 44 040\
     0171 1101111 117 100000 1110111 0141 0156 1110100 32 0164 6f 32 6b 1101110 1101111 1110111 100000\
     0164 1101000 0145 040 0146 6c 97 1100111 2c 100000 0144 111 110 100111 116 100000 1111001 6f 117\
     63 0110 1100101 0162 0145 100000 1111001 111 117 100000 97 114 0145 46 1010011 0105 0103 67 79\
     1001110 123 87 110011 110001 67 110000 1001101 32 55 060 100000 110111 0110 110011 32 53 51 0103\
     0103 060 0116 040 5a 0117 73 0101 7d 1001000 0141 1110110 1100101 100000 102 0165 0156 33'
     
flag = ""
for _ in c.split(' '):
  if len(_) == 2 and _[1:].isalpha(): #HEX
    flag += _.decode('hex')
  if (len(_) == 2 and not _[1:].isalpha()) or (len(_) == 3 and int(_[0]) != 0): #DEC
    flag += chr(int(_))
  if len(_) == 4 or (len(_) == 3 and int(_[0]) == 0) : #OCT
    flag += chr(int(_, 8))
  if len(_) > 4: #BIN
    flag += binascii.unhexlify('%x' % int(_,2))
print(flag)
```
# 自主學習主題

## alexctf-2017: CR1: Ultracoded 50
```
! wget https://raw.githubusercontent.com/ctfs/write-ups-2017/master/alexctf-2017/cryptography/cr1-ultracoded-50/zero_one

!pip install pwntools

!pip install morse_talk
```
```
#!/usr/bin/env python

import binascii
import base64
import morse_talk as mtalk

with open('./zero_one', 'r') as content_file:
    bin_text = content_file.read()

bin_text = bin_text.replace("ZERO","0")
bin_text = bin_text.replace("ONE","1")
bin_text = bin_text.replace(" ","")
bin_text = bin_text.strip()

print "Binary : "+ bin_text
b64 = ''.join(chr(int(bin_text[i:i+8], 2)) for i in range(0, len(bin_text), 8))
print "Base 64 : "+ b64
print "morse : " + base64.b64decode(b64).decode('utf-8')

mtalk.decode(base64.b64decode(b64).decode('utf-8'))
```
# easyctf-2017: Decode Me - 100 points
```
Someone I met today told me that they had a perfect encryption method. 
To prove that there is no such thing, 
I want you to decrypt this encrypted flag he gave me.

附檔已整理在

https://raw.githubusercontent.com/easyctf/easyctf-2017-problems/master/decode-me/encrypted_flag.txt

```
```
!wget https://raw.githubusercontent.com/easyctf/easyctf-2017-problems/master/decode-me/encrypted_flag.txt

!cat encrypted_flag.txt
```
```
import base64

a = open('encrypted_flag.txt').read()
a

import base64

a = open('encrypted_flag.txt').read()
a = a.replace('\n','').replace('\\n','')
b64 = str(base64.standard_b64decode(a),'utf-8')

b64
```
```
import base64

a = open('encrypted_flag.txt').read()
a = a.replace('\n','').replace('\\n','')
b64 = str(base64.standard_b64decode(a),'utf-8')

while 'easyctf' not in b64:
    b64 = str(base64.standard_b64decode(b64),'utf-8')
print(b64)
```
```
import base64

a = open('encrypted_flag.txt').read()
a = a.replace('\n','').replace('\\n','')
b64 = str(base64.standard_b64decode(a),'utf-8')


b64_2 = str(base64.standard_b64decode(b64),'utf-8')

b64_3 = str(base64.standard_b64decode(b64),'utf-8')
print(b64_3)
```
# [進階主題]

## Base 64 模組編碼與解碼趣味遊戲

## 雙重編碼(Doubly decoded)
```
import base64

data =b'BreakAllCTF{HappyPythonDay}'
encoded_data = base64.b64encode(data)
encoded_data2 = base64.b64encode(encoded_data)

print('Original Data :', data)
print('Encoded :', encoded_data)
print('Doubly Encoded :', encoded_data2)

decoded_data = base64.b64decode(encoded_data2)
result = base64.b64decode(decoded_data)
print(result)
```
### 自己的CTF自己出:
```
答案是BreakAllCTF{HappyPythonDay!A-LO_HA}

BreakALLCTF{HappyPythonDay}

請提供數字要學員解答
```
```
s = 'BreakALLCTF{HappyPythonDay}'

#result = ''
for _ in s:
#  result += ord(_)
#  result
  print(ord(_))
```

### 答案要以二進位(bin)八進位(oct)十六進位(hex)表示
```
s = 'BreakALLCTF{HappyPythonDay}'

#result = ''
for _ in s:
#  result += ord(_)
#  result
  print(bin(ord(_)))
#print(oct(ord(_)))
#print(hex(ord(_)))
```
### 試分析看看底下程式的意義
```
#!/usr/bin/python
import base64

c = '0b1000010 0b1110010 0b1100101 0b1100001 0b1101011 0b1000001 0b1001100 0b1001100 0b1000011 0b1010100 0b1000110 0b1111011 0b1001000 0b1100001 0b1110000 0b1110000 0b1111001 0b1010000 0b1111001 0b1110100 0b1101000 0b1101111 0b1101110 0b1000100 0b1100001 0b1111001 0b1111101'


flag2 = ''
for _ in c.split(' '):
   flag2 += chr(int(_,2))
    
flag2
```
```
c = '0b1000010'
flag = chr(int(c,2))
flag
```
### 參考底下程式,完成 Crypto 101:Morse code
```
Morse Code Translator In Python

https://www.geeksforgeeks.org/morse-code-translator-python/
```
### Python program to implement Morse Code Translator 
```
"""
VARIABLE KEY 
'cipher' -> 'stores the morse translated form of the english string' 
'decipher' -> 'stores the english translated form of the morse string' 
'citext' -> 'stores morse code of a single character' 
'i' -> 'keeps count of the spaces between morse characters' 
'message' -> 'stores the string to be encoded or decoded' 
"""
  
# 使用字典(Dictionary)資料型態來表達 morse 編碼 
MORSE_CODE_DICT = { 'A':'.-', 'B':'-...', 
                    'C':'-.-.', 'D':'-..', 'E':'.', 
                    'F':'..-.', 'G':'--.', 'H':'....', 
                    'I':'..', 'J':'.---', 'K':'-.-', 
                    'L':'.-..', 'M':'--', 'N':'-.', 
                    'O':'---', 'P':'.--.', 'Q':'--.-', 
                    'R':'.-.', 'S':'...', 'T':'-', 
                    'U':'..-', 'V':'...-', 'W':'.--', 
                    'X':'-..-', 'Y':'-.--', 'Z':'--..', 
                    '1':'.----', '2':'..---', '3':'...--', 
                    '4':'....-', '5':'.....', '6':'-....', 
                    '7':'--...', '8':'---..', '9':'----.', 
                    '0':'-----', ', ':'--..--', '.':'.-.-.-', 
                    '?':'..--..', '/':'-..-.', '-':'-....-', 
                    '(':'-.--.', ')':'-.--.-'} 
  
# 定義morse 編碼的函數 
def encrypt(message): 
    cipher = '' 
    for letter in message: 
        if letter != ' ': 
  
            # Looks up the dictionary and adds the 
            # correspponding morse code 
            # along with a space to separate 
            # morse codes for different characters 
            cipher += MORSE_CODE_DICT[letter] + ' '
        else: 
            # 1 space indicates different characters 
            # and 2 indicates different words 
            cipher += ' '
  
    return cipher 

# 定義morse 解碼的函數   
def decrypt(message): 
  
    # extra space added at the end to access the 
    # last morse code 
    message += ' '
  
    decipher = '' 
    citext = '' 
    for letter in message: 
  
        # checks for space 
        if (letter != ' '): 
  
            # counter to keep track of space 
            i = 0
  
            # storing morse code of a single character 
            citext += letter 
  
        # in case of space 
        else: 
            # if i = 1 that indicates a new character 
            i += 1
  
            # if i = 2 that indicates a new word 
            if i == 2 : 
  
                 # adding space to separate words 
                decipher += ' '
            else: 
  
                # accessing the keys using their values (reverse of encryption) 
                decipher += list(MORSE_CODE_DICT.keys())[list(MORSE_CODE_DICT 
                .values()).index(citext)] 
                citext = '' 
  
    return decipher 
  
# 

message = "HappyPythonDay"
result = encrypt(message.upper()) 
print (result) 
  
message = ".... .- .--. .--. -.-- .--. -.-- - .... --- -. -.. .- -.--"
result = decrypt(message) 
print (result) 
```
```
# Hard-coded driver function to run the program 
def main(): 
    
#message = "BreakAllCTF{HappyPythonDay}"
message = "HappyPythonDay"
result = encrypt(message.upper()) 
print (result) 
  
message = ".... .- .--. .--. -.-- .--. -.-- - .... --- -. -.. .- -.--"
result = decrypt(message) 
print (result) 
  
# Executes the main function 
if __name__ == '__main__': 
   main()
```
