


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


but curl need ssl to be installed on /usr/local/ssl

curl install

```
./configure --with-ssl
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDE5MjM1MzE3LC0xNzQ5MTMwMDYsNTc0MT
ExNjUzLC0xNzgyODg4MjgxLDk4NjQwNDY2LDE0NjcwNTA0Mjks
MTQwMjc0MTI0MiwtMjE1ODc2NjczLC0xOTU3MjI1MzMxLC0xNj
YzMzAwNjQ2LDIyMzA4MjQ2MSwxNTU2NTE5OTEyLC04NDcwMDA5
MTYsMjEwMjIxMTIyMSwtMjY3Njk1NTY4XX0=
-->