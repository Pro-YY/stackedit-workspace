


> Written with [StackEdit](https://stackedit.io/).
```
2019-04-21 18:08:57 INFO     loading libcrypto from libcrypto.so.1.1
Traceback (most recent call last):
  File "/usr/local/bin/sslocal", line 11, in <module>
    load_entry_point('shadowsocks==2.8.2', 'console_scripts', 'sslocal')()
  File "/usr/local/lib/python3.6/dist-packages/shadowsocks/local.py", line 39, in main
    config = shell.get_config(True)
  File "/usr/local/lib/python3.6/dist-packages/shadowsocks/shell.py", line 262, in get_config
    check_config(config, is_local)
  File "/usr/local/lib/python3.6/dist-packages/shadowsocks/shell.py", line 124, in check_config
    encrypt.try_cipher(config['password'], config['method'])
  File "/usr/local/lib/python3.6/dist-packages/shadowsocks/encrypt.py", line 44, in try_cipher
    Encryptor(key, method)
  File "/usr/local/lib/python3.6/dist-packages/shadowsocks/encrypt.py", line 83, in __init__
    random_string(self._method_info[1]))
  File "/usr/local/lib/python3.6/dist-packages/shadowsocks/encrypt.py", line 109, in get_cipher
    return m[2](method, key, iv, op)
  File "/usr/local/lib/python3.6/dist-packages/shadowsocks/crypto/openssl.py", line 76, in __init__
    load_openssl()
  File "/usr/local/lib/python3.6/dist-packages/shadowsocks/crypto/openssl.py", line 52, in load_openssl
    libcrypto.EVP_CIPHER_CTX_cleanup.argtypes = (c_void_p,)
  File "/usr/lib/python3.6/ctypes/__init__.py", line 361, in __getattr__
    func = self.__getitem__(name)
  File "/usr/lib/python3.6/ctypes/__init__.py", line 366, in __getitem__
    func = self._FuncPtr((name_or_ordinal, self))
AttributeError: /usr/lib/x86_64-linux-gnu/libcrypto.so.1.1: undefined symbol: EVP_CIPHER_CTX_cleanup

```


```
/usr/include/openssl/evp.h:#  define EVP_CIPHER_CTX_init(c)      EVP_CIPHER_CTX_reset(c)
/usr/include/openssl/evp.h:#  define EVP_CIPHER_CTX_cleanup(c)   EVP_CIPHER_CTX_reset(c)
/usr/include/openssl/evp.h:int EVP_CIPHER_CTX_reset(EVP_CIPHER_CTX *c);
````

line 52, line 111
EVP_CIPHER_CTX_cleanup -> EVP_CIPHER_CTX_reset
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI4NzMwNjYxXX0=
-->