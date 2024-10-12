# FlyVerify-api-php-client

## FAQ:

1.PHP8.3.4 +OpenSSL 3.2.1解密失败

```
# openssl解密失败处理
# 1.查看openssl.cnf配置文件
php -i | grep openssl.cnf
Openssl default config => /opt/homebrew/etc/openssl@3/openssl.cnf


# 2.修改配置
openssl_conf = openssl_init

[openssl_init]
providers = provider_sect
   
[provider_sect]
default = default_sect
legacy = legacy_sect 	// 默认无，新增配置
   
[default_sect]
activate = 1			// 默认注释，开启
   
[legacy_sect]
activate = 1 			// 默认无，新增配置


# 3.修改完重启php-fpm
```

