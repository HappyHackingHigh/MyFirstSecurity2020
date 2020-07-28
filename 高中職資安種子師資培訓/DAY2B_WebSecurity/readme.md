# 模組四:網站安全 Web Security
```
4.1.網站運作原理

4.2.網站測試工具實戰
4.3.Web-CTF實戰

4.4.網站攻擊分析與安全防禦技術
4.5.網站漏洞分析與測試DVWA

4.6.應用程式防火牆實戰[錄影教學]
```
# 4.1.網站運作原理
```
瀏覽器與伺服器
前端(Frontend)
後端(Backend)

網站基本組成
網站伺服器(web server)
伺服器端程式(Client-side Programming)
客戶端程式(server-side Programming)

HTTP 超文本傳輸協定 HyperText Transfer Protocol
HTTP 協定(HTTP Protocol)
HTTP 請求(HTTP Request)
HTTP 回應(HTTP Response)
```
```
HTTP status codes HTTP狀態碼
1	1xx訊息 informational response – the request was received, continuing process
2	2xx成功 successful – the request was successfully received, understood, and accepted
3	3xx重新導向 redirection – further action needs to be taken in order to complete the request
4	4xx客戶端錯誤 client error – the request contains bad syntax or cannot be fulfilled
5	5xx伺服器錯誤 server error – the server failed to fulfil an apparently valid request 
```
```
進階主題: HTTPS

HTTPS 權威指南：在服務器和 Web 應用上部署 SSL/TLS 和 PKI 
HTTPS权威指南 在服务器和Web应用上部署SSL TLS和PKI
伊萬·裡斯蒂奇 (Ivan Risti?) 人民郵電

深入淺出 HTTPS : 從原理到實戰 深入浅出HTTPS:从原理到实战
虞衛東 電子工業 2018-06-01
```
# 4.2.網站測試工具實戰
```
A.強大的HTTP命令行工具：CURL
	A.1.Windows安裝過程
	A.2.實測案例
B.強大的封包攔截工具：Burp Suite
	B.1.Windows安裝過程
	B.2.實測案例
C.強大的網頁偵測工具：Developer Tools
	C.1.實測案例
```
# 4.3.Web-CTF實戰
```

```
# 4.4.網站攻擊分析與安全防禦技術
```
[1]網站漏洞OWASP TOP 10
[2]測試環境建置 Kali Linux + Docker +DVWA
[3]網站威脅模式與LOG分析

[4]強化網站安全的技術
```
# 4.5.網站漏洞分析與測試DVWA
```
COMMAND INJECTION
SQLI
XSS
LFI
```
```
網站log 分析
```

# 4.6.網站應用程式防火牆實戰[錄影教學]
```
[0]ModSecurity網站應用程式防火牆
   ModSecurity WAF
   安裝ModSecurity
   規則設定
[1]實戰環境建置
[2]sqli 攻防實戰
   未啟動ModSecurity====可以進行SQLi攻擊
   啟動ModSecurity====SQLi攻擊被阻擋下來
   察看日誌檔ModSecurity log
     sudo cat /var/log/apache2/modsec_audit.log
```
