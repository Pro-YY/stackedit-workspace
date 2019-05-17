


> Written with [StackEdit](https://stackedit.io/).


1 买机器
S4.SMALL2

2 设置域名解析
A record: t1.ezouqi.com

3 证书申请

centos 7.5
```
yum install certbot
time certbot certonly --standalone -n -m brookeyang@tencent.com --agree-tos -d t1.ezouqi.com --dry-ru
```

ubuntu 18.04


4 配置nginx
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2Mzc5NzA0NzgsLTg0NzAwMDkxNiwyMT
AyMjExMjIxLC0yNjc2OTU1NjhdfQ==
-->