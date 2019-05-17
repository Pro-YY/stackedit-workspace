


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

nginx 1.12.2 no support for v1.3

v1.13


nginx : 1.16.0 install
```
yum install gcc pcre-devel zlib-devel openssl-devel
wget http://nginx.org/download/nginx-1.16.0.tar.gz
tar -zxvf nginx-1.16.0.tar.gz
./configure --with-http_v2_module --with-http_ssl_module
./configure --with-http_v2_module --with-http_ssl_module --with-openssl=/root/openssl-1.1.1b
make -j2
make install

cd /usr/local/nginx
./sbin/nginx -V
./sbin/nginx -t
./sbin/nginx
```
compile


v1.3 openssl

```
wget https://www.openssl.org/source/openssl-1.1.1b.tar.gz
tar -zxvf openssl-1.1.1b.tar.gz
```
no need to compile alone, nginx will compile it


install curl 

NOTE: but curl need ssl to be make (no need to make install)

curl install
```
./configure --with-ssl
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE3MjgwNTE3NSwtODk5ODI1MDAzLDQxOT
IzNTMxNywtMTc0OTEzMDA2LDU3NDExMTY1MywtMTc4Mjg4ODI4
MSw5ODY0MDQ2NiwxNDY3MDUwNDI5LDE0MDI3NDEyNDIsLTIxNT
g3NjY3MywtMTk1NzIyNTMzMSwtMTY2MzMwMDY0NiwyMjMwODI0
NjEsMTU1NjUxOTkxMiwtODQ3MDAwOTE2LDIxMDIyMTEyMjEsLT
I2NzY5NTU2OF19
-->