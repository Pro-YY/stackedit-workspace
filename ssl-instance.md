


> Written with [StackEdit](https://stackedit.io/).


1 买机器
S4.SMALL2

2 设置域名解析
A record: t1.ezouqi.com

3 证书申请

centos 7.5
```
yum install certbot
time certbot certonly --standalone -n -m brookeyang@tencent.com --agree-tos -d t1.ezouqi.com
systemctl start certbot-renew.timer
```
/etc/letsencrypt/live/t1.ezouqi.com/fullchain.pem
/etc/letsencrypt/live/t1.ezouqi.com/privkey.pem


ubuntu 18.04
TODO

4 配置nginx
yum install nginx

http2
https
ipv6

<!--stackedit_data:
eyJoaXN0b3J5IjpbODM0NTc4NjY3LC04NDcwMDA5MTYsMjEwMj
IxMTIyMSwtMjY3Njk1NTY4XX0=
-->