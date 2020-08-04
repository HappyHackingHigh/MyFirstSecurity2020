# 模組三:網路安全
```
3.1.網路概論==基本觀念

3.2.網路封包分析實戰wireshark網路封包分析
3.3.Network-CTF實戰

3.4.網路攻擊分析與安全防護技術
3.5.防火牆防禦實戰[錄影教學]
3.6.入侵偵測系統資安防禦實戰[錄影教學]
```
# 3.1.網路概論
```
本課程將介紹
[1]基礎的網路概念:
     包含網路類型、網路拓樸、網路架構、網路傳輸媒介等
[2]網路協定:包括OSI 模型與TCP/IP網路協定
    使同學對網路能有更進一步的認識。

1. 瞭解電腦網路類型及現代相關應用
2. 瞭解訊息傳遞方式並能說明網路協定每一層的功能
3. 瞭解TCP、UDP、IP協定與之特性
4. 瞭解IP、DNS運作原理
```

```
A.1. 電腦通訊概說
   A.1.1.電腦與網路:基本觀念
   A.1.2.資訊傳輸模式
   A.1.3.網路傳輸速度
   A.1.4.電腦網路的類型
A.2. 網路的組成與架構
   A.2.1. 電腦網路的功能
   A.2.2. 區域網路的拓樸
   A.2.3. 電腦網路分享架構:Client/server與P2P

A.3. 網路標準與通訊協定
   A.3.1.通訊協定與標準
   A.3.2. OSI通訊標準
   A.3.3. TCP/IP協定
   
   A.3.4. 傳輸層重要協定:TCP vs UDP
        A.3.4.1 TCP vs UDP
	A.3.4.2 TCP/UDP埠列表:https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers
        A.3.4.3 TCP的三向交握
	
   A.3.5. IP與DNS(網域名稱)
        A.3.5.1. IP協定與IP位址
        A.3.5.2. DNS
```
# 3.2.網路封包分析實戰wireshark網路封包分析
```
本課程以 wireshark教導學生，讓學生由實作中了解TCP/IP網路協定
課程提供Connection2Google.pcap封包檔作為實戰分析的範例
學生須完成：
[1] DNS查詢分析
[2] TCP 三向交握分析
[3] UDP封包格式分析
[4] IP封包格式分析

B.1. Wireshark 封包側錄
	 B.1.1.安裝Wireshark
	 B.1.2.封包側錄
	 B.1.3.Wireshark基本技術
	       Capture filter
	       Display filter
	       Follow TCP stream
B.2.測試情境與分析:Connect2Google
	B.2.1. Wireshark 封包分析Connect2Google
	B.2.2. DNS查詢分析
	B.2.3. TCP 三向交握分析
	B.2.4. UDP封包格式分析
	B.2.5. IP封包格式分析
B.3.FTP 側錄實務
B.4.Telnet 側錄實務
B.5.網路攻擊封包分析:DDoS
```
```
NAPA證照: 網路安全封包分析認證課程
Network Security of Packet Analysis Course
https://www.uuu.com.tw/Course/Show/930/網路安全封包分析認證課程
```
```

https://www.tenlong.com.tw/search?utf8=%E2%9C%93&keyword=wireshark

網路分析完全實戰手冊 ─ 使用 Wireshark, 2/e 
Network Analysis using Wireshark 2 Cookbook, 2/e
Nagendra Kumar Nainar、Yogesh Ramdoss、Yoram Orzach
孫餘強、王濤 博碩文化2019-06-17
```

# 3.3.Network-CTF實戰
```
Internetwache-CTF-2016:Network Forensic
PicoCTF_2017-Special Agent User
```
```
HITCON 2017 CTF Data & Mining :strings XXXXX | grep hitcon
https://balsn.tw/ctf_writeup/20171104-hitconctfquals/
```
# 3.4.網路攻擊模式分析與防禦
```
本課程模組提供網路攻擊分析與安全防禦的基本觀念:

[1]網路攻擊模式分析
      APT
      Ransomeware
      DDOS
      社交工程
       ....
      MITRE ATT@CK Framework

[2]網路資安防禦技術
      防火牆
      入侵偵測系統
      ............
```
### 技服簡報
```
教材下載: https://www.nccst.nat.gov.tw/Handout?lang=zh
政府組態基準(Government Configuration Baseline，簡稱GCB):
https://www.nccst.nat.gov.tw/GCB

資安職能:https://ctts.nccst.nat.gov.tw/
https://ctts.nccst.nat.gov.tw/Download

https://ctts.nccst.nat.gov.tw/Download
```
### MITRE ATT@CK Framework
```
用MITRE ATT&CK框架識別攻擊鏈，讓入侵手法描述有一致標準
https://www.ithome.com.tw/article/129614

由MITRE提出的ATT&CK資安框架，不僅是讓威脅入侵的描述具有更一致的標準，
成為有助於理解攻擊者具備能力的知識庫，並能為攻防演練帶來幫助。
而且，在去年(2018)的ATT＆CK評估計畫中，可進一步成為衡量安全產品的方式，
目前已有9家業者端點安全產品參與。
```

### NIST Cybersecurity Framework（CSF）
```
https://www.nist.gov/cyberframework/framework
https://s.itho.me/events/2019/cybersec101/0906_0910.pdf
https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.04162018.pdf
```
```
美國 國家標準與技術研究所（NIST）提出的網路安全框架
當今值得企業參考的資安架構
針對Critical Infrastructure 的Cybersecurity風險評估共通標準，以風險為導向、持續運作的管理架構
```
```
【NIST CSF導入關鍵】7步驟打造整體安全防護網，從盤點現況與成熟度評估著手
https://www.ithome.com.tw/news/133172
```
```
【資安框架】NIST CSF 1.1：英美各國政府和一般企業都相繼採用的網路安全框架
https://www.ithome.com.tw/article/129614

為了強化關鍵基礎設施的資訊安全，美國政府制訂的網路安全框架（Cybersecurity Framework，CSF），
其內容涵蓋一般網路環境中，需要執行資安防護的面向，
雖然推出才5年，如今，不只美國聯邦政府自己廣泛應用，英國、義大利、以色列、日本等國的公部門與企業，
也導入了這個框架，管控網路環境的資訊安全。

這個網路安全框架的起源，來自於美國前總統歐巴馬2013年2月時，所發布的第13636號行政命令（EO），
為了改善關鍵基礎設施的網路安全，下令國家標準暨技術研究院（NIST）根據現有的標準與指南，
訂立一套可供相關單位採用的資安框架，能夠藉此強化網路安全。
```
