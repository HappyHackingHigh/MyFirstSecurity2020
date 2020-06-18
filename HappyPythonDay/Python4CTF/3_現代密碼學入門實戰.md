# 現代密碼學入門實戰Introduction to Modern Cryptography
```
學習目標:
[1]學生上完課後應該對底下密碼學運作機制有所了解
1.對稱式密碼
2.非對稱式密碼[公開金鑰Public Key]
3.Hashing雜湊法

[2]熟悉使用Python/pycrypto第三方套件完成上述密碼學的運作

註:本課程僅介紹相關加解密技術,
相關演算法及其實作請自行參閱大學密碼學教科書
```


# pycrypto第三方套件
```
[A]官方網址: https://pypi.org/project/pycrypto/

[B]pycrypto模組支援的加密方式[僅摘錄部份]
   [B1]Hashing[雜湊值|散列值]： MD5   SHA     HMAC
   [B2]對稱加密方式：AES   DES  3DES   ARC4
   [3]公開金鑰加密和簽名：RSA   DSA
[C]pycrypto安裝
   !pip list
   !pip install pycrypto
```

# [1]Hashing

###  使用MD5
```
https://blog.csdn.net/lxgwm2008/article/details/9287481


from Crypto.Hash import MD5
MD5.new('abc').hexdigest()

from Crypto.Hash import MD5
MD5.new('Abc').hexdigest()

from Crypto.Hash import MD5
MD5.new('Abccxczxczxczxcxzczxczxczxczxczxczxczxcxz').hexdigest()
```
### 使用SHA"""
```
from Crypto.Hash import SHA256

hash = SHA256.new()
hash.update('b cvxzv dfgnhgsdf mghfs hgdf ')

hash.digest()
```

# [1]Public KEY

# RSA

### 產生key Pairs
```
from Crypto.PublicKey import RSA
from Crypto import Random

random_generator = Random.new().read
key = RSA.generate(1024, random_generator)
key

key.n

key.p

key.can_encrypt()

key.can_sign()

key.has_private()

public_key = key.publickey()

public_key
```

### 使用公鑰來加密
```
enc_data = public_key.encrypt('HappyPythonDay', 32)
enc_data

```
### 使用私鑰來解密
```
key.decrypt(enc_data)
```

# 對稱式金鑰

## AES加密與解密
```
[1]進階加密標準(Advanced Encryption Standard, AES)
[2]在密碼學中又稱Rijndael加密法
[3]是美國聯邦政府採用的一種區段加密標準。
[4]這個標準用來替代原先的DES，已經被多方分析且廣為全世界所使用。

https://zh.wikipedia.org/zh-tw/%E9%AB%98%E7%BA%A7%E5%8A%A0%E5%AF%86%E6%A0%87%E5%87%86
```
```
from Crypto.Cipher import AES

obj = AES.new('This is a key123', AES.MODE_CBC, 'This is an IV456')

message = "BreakALLCTF{happyHackingDay}"

ciphertext = obj.encrypt(message)

ciphertext
```
```
from Crypto.Cipher import AES

obj = AES.new('This is a key123', AES.MODE_CBC, 'This is an IV456')

message = "The answer is no"

ciphertext = obj.encrypt(message)

ciphertext
```
```
obj2 = AES.new('This is a key123', AES.MODE_CBC, 'This is an IV456')
obj2.decrypt(ciphertext)
```

# PicoCTF_2017: ComputeAES

```
You found this clue laying around. Can you decrypt it?
```

```
Encrypted with AES in ECB mode. All values base64 encoded
ciphertext = rW4q3swEuIOEy8RTIp/DCMdNPtdYopSRXKSLYnX9NQe8z+LMsZ6Mx/x8pwGwofdZ
key = 6v3TyEgjUcQRnWuIhjdTBA==
```
```
Hint:Try online tools or python

https://github.com/lflare/picoctf_2017_writeup/blob/master/cryptography/computeaes/decrypt.py
```
```
#! /usr/bin/env python3
##
# Script for PicoCTF computeAES challenge
# Created by Amos (LFlare) Ng
##
# Requires pycrypto
import base64
from Crypto.Cipher import AES

key = base64.b64decode("6v3TyEgjUcQRnWuIhjdTBA==")
ciphertext = base64.b64decode("rW4q3swEuIOEy8RTIp/DCMdNPtdYopSRXKSLYnX9NQe8z+LMsZ6Mx/x8pwGwofdZ")

crypter = AES.new(key, AES.MODE_ECB)
plaintext = crypter.decrypt(ciphertext).decode("utf-8")

print(plaintext)
```

# 自主學習主題

### random number generator
```
https://pypi.org/project/pycrypto/


from Crypto import Random
rndfile = Random.new()
rndfile.read(16)

from Crypto.Random import random
random.choice(['dogs', 'cats', 'bears'])
```
##  DES對稱式碼加解密實戰
```
from Crypto.Cipher import DES

des = DES.new('01234567', DES.MODE_ECB)

text = 'BrCTF{HappyHack}'

print("待加密的明文:%s" %text)
cipher_text = des.encrypt(text)

print("加密後的密文:%s" %cipher_text)

plain_text = des.decrypt(cipher_text)
print("解密後的答案:%s" %plain_text)

```
##  3DES對稱式碼加解密實戰
```

# -*- Encoding: utf-8 -*-

from Crypto.Cipher import DES3

BS = DES3.block_size

pad = lambda s: s + (BS - len(s) % BS) * chr(BS - len(s) % BS)
unpad = lambda s : s[0:-ord(s[-1])]

key = 'a' * 16
text = 'Hello, there!'

cipher = DES3.new(key, DES3.MODE_ECB)

encrypted_text = cipher.encrypt(pad(text))
decrypted_text = unpad(cipher.decrypt(encrypted_text))

assert text == decrypted_text

encrypted_text

decrypted_text

```
## ARC4 Stream ciphers
```
https://blog.csdn.net/lxgwm2008/article/details/9287481


from Crypto.Cipher import ARC4

obj1 = ARC4.new('01234567')

obj2 = ARC4.new('01234567')

text = 'abcdefghijklmnop'

cipher_text = obj1.encrypt(text)

cipher_text

obj2.decrypt(cipher_text)

```
#  範例
```
https://blog.csdn.net/werewolf_st/article/details/45935913

# !/usr/bin/env python
# coding: utf-8

from Crypto.Cipher import AES
from binascii import b2a_hex, a2b_hex

class MyCrypt():
    def __init__(self, key):
        self.key = key
        self.mode = AES.MODE_CBC

    def myencrypt(self, text):
        length = 16
        count = len(text)
        print count
        if count < length:
            add = length - count
            text= text + ('\0' * add)

        elif count > length:
            add = (length -(count % length))
            text= text + ('\0' * add)

        # print len(text)
        cryptor = AES.new(self.key, self.mode, b'0000000000000000')
        self.ciphertext = cryptor.encrypt(text)
        return b2a_hex(self.ciphertext)

    def mydecrypt(self, text):
        cryptor = AES.new(self.key, self.mode, b'0000000000000000')
        plain_text = cryptor.decrypt(a2b_hex(text))
        return plain_text.rstrip('\0')

if __name__ == '__main__':
    mycrypt = MyCrypt('abcdefghjklmnopq')
    e = mycrypt.myencrypt('hello,world!')
    d = mycrypt.mydecrypt(e)
    print e
    print d
 ```
