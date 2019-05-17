


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
v1.3 handh
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk4NTA5Mzg5OCwxODk5MTkyMTA3LDExNz
I4MDUxNzUsLTg5OTgyNTAwMyw0MTkyMzUzMTcsLTE3NDkxMzAw
Niw1NzQxMTE2NTMsLTE3ODI4ODgyODEsOTg2NDA0NjYsMTQ2Nz
A1MDQyOSwxNDAyNzQxMjQyLC0yMTU4NzY2NzMsLTE5NTcyMjUz
MzEsLTE2NjMzMDA2NDYsMjIzMDgyNDYxLDE1NTY1MTk5MTIsLT
g0NzAwMDkxNiwyMTAyMjExMjIxLC0yNjc2OTU1NjhdfQ==
-->