


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
```
yum install nginx
# edit conf
systemctl restart nginx.service
```
http2
https
ipv6

https://t1.ezouqi.com/(https://t1.ezouqi.com/)

nginx conf server block, 80 redirect
```
```

verify chrome tools/extension

nginx 1.12.2 no 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MTk3OTk3NTAsMjIzMDgyNDYxLDE1NT
Y1MTk5MTIsLTg0NzAwMDkxNiwyMTAyMjExMjIxLC0yNjc2OTU1
NjhdfQ==
-->