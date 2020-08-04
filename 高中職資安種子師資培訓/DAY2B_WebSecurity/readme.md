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
伺服器端程式(Client-side Programming):HTML CSS3 JAVASCRIPT
客戶端程式(server-side Programming)  PHP  ASP.NET

HTTP 超文本傳輸協定 HyperText Transfer Protocol
HTTP 協定(HTTP Protocol)
HTTP 請求(HTTP Request)
HTTP 回應(HTTP Response)
```
### HTTP 請求(HTTP Request)
```
HTTP 0.9 這個版本只有GET方法
HTTP 1.0 這個版本有GET HEAD POST這三個方法
HTTP 1.1 這個版本是當前版本，包含GET HEAD POST OPTIONS PUT DELETE TRACE CONNECT這8個方法

HTTP/2
```
```
http method
https://developer.mozilla.org/zh-TW/docs/Web/HTTP/Methods


[1]GET 方法請求展示指定資源。使用 GET 的請求只應用於取得資料。
[2]HEAD 方法請求與 GET 方法相同的回應，但它沒有回應主體（response body）。
[3]POST 方法用於提交指定資源的實體，通常會改變伺服器的狀態或副作用（side effect）。
[4]PUT 方法會取代指定資源所酬載請求（request payload）的所有表現。

[5]DELETE 方法會刪除指定資源.

[6]CONNECT 方法會和指定資源標明的伺服器之間，建立隧道（tunnel）。

[7]OPTIONS 方法描述指定資源的溝通方法（communication option）。

TRACE 方法會與指定資源標明的伺服器之間，執行迴路返回測試（loop-back test）。
PATCH
PATCH 方法套用指定資源的部份修改。
```
```
https://httpbin.org/
```
```
HTTP header fields
https://en.wikipedia.org/wiki/List_of_HTTP_header_fields
```
### HTTP 回應(HTTP Response)
```
HTTP status codes HTTP狀態碼
1xx訊息 informational response – the request was received, continuing process
2xx成功 successful – the request was successfully received, understood, and accepted
3xx重新導向 redirection – further action needs to be taken in order to complete the request
4xx客戶端錯誤 client error – the request contains bad syntax or cannot be fulfilled
5xx伺服器錯誤 server error – the server failed to fulfil an apparently valid request 
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
