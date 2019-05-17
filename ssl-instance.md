


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

## nginx systemd

compile args:
--pid-path=/run/nginx.pid

 /lib/systemd/system/nginx.service
```
 
```




v1.3 openssl

```
wget https://www.openssl.org/source/openssl-1.1.1b.tar.gz
tar -zxvf openssl-1.1.1b.tar.gz
```
no need to compile alone, nginx will compile it

# TODO later
with openssl 1.1.1b for tlsv.1.3
with http2

install curl 

NOTE: but curl need ssl to be make and install to an seperate dir

like: configure with prefix=/root/install/ssl

curl install


[https://curl.haxx.se/docs/install.html](https://curl.haxx.se/docs/install.html)

```
./configure --with-ssl=/root/install/ssl

```

# tls 1.2 vs 1.3
v1.3 handshake
```
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384

```

v1.2 handshake
```
* TLSv1.2 (OUT), TLS handshake, Client hello (1):
* TLSv1.2 (IN), TLS handshake, Server hello (2):
* TLSv1.2 (IN), TLS handshake, Certificate (11):
* TLSv1.2 (IN), TLS handshake, Server key exchange (12):
* TLSv1.2 (IN), TLS handshake, Server finished (14):
* TLSv1.2 (OUT), TLS handshake, Client key exchange (16):
* TLSv1.2 (OUT), TLS change cipher, Client hello (1):
* TLSv1.2 (OUT), TLS handshake, Finished (20):
* TLSv1.2 (IN), TLS handshake, Finished (20):
* SSL connection using TLSv1.2 / ECDHE-RSA-AES256-GCM-SHA384
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTI0NjQ2OTgwLC0yMDE3NDIyNjI5LDE4OT
kxOTIxMDcsMTE3MjgwNTE3NSwtODk5ODI1MDAzLDQxOTIzNTMx
NywtMTc0OTEzMDA2LDU3NDExMTY1MywtMTc4Mjg4ODI4MSw5OD
Y0MDQ2NiwxNDY3MDUwNDI5LDE0MDI3NDEyNDIsLTIxNTg3NjY3
MywtMTk1NzIyNTMzMSwtMTY2MzMwMDY0NiwyMjMwODI0NjEsMT
U1NjUxOTkxMiwtODQ3MDAwOTE2LDIxMDIyMTEyMjEsLTI2NzY5
NTU2OF19
-->