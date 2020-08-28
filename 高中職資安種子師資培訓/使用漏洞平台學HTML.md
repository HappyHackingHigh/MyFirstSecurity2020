# 使用DVWA漏洞平台學HTML
```
DVWA XSS漏洞

[1]注入各式HTML標籤


[2]跑馬燈
https://www.wibibi.com/info.php?tid=68

```
```
進階款式（參數可以設定要跑的方向與速度）
<marquee 這裡放參數設定>這裡放要跑的文字</marquee>

HTML marquee 跑馬燈可用的參數如下
方向設定：direction="參數值"；可設定 up（向上）、dun（向下）、left（向左）、right（向右）。
對齊設定：align="參數值"；可設定 top（向上對齊）、midden（垂直至中）、botton（向下對齊）。
速度設定：scrollamount="參數值" ；可設定為數字，通常設定 1~10 的範圍，數字越大跑得越快。
長度設定：height="參數值"；數字，自行設定。
寬度設定：width="參數值"；數字，自行設定。
行為設定：behavior="參數值"；可設定 alternate（來回跑）、slide（跑入後停止）。
背景顏色：bgcolor="參數值"；可設定為顏色的色碼，不設定則沒有顏色。


HTML marquee 跑馬燈範例
<marquee direction="right" height="30" scrollamount="5" behavior="alternate">跑馬燈測試</marquee>
```
