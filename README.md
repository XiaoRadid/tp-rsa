### tp-rsa 加密解密数据方法
> 第一次使用需要手动生成公钥和私钥

> 1.0.9 修复win下openssl.cnf文件不存在的问题

```shell script
php think rsa:create
```
```php

function test(){
    $rsa = new \xiaoradid\rsa\Auth();
    $str = "sssss";   
    // 私钥加密
    $enStr = $rsa->pkEncrypt($str);
    // 公钥解密
    $rsa->puDecrypt($enStr);
    // 公钥加密
    $pu = $rsa->puEncrypt($str);
    // 私钥解密
    $rsa->pkDecrypt($pu);
}
```
> 已经封装到助手函数 
```php
function test1(){
    $str = "sssss";
    // 私钥加密
    $enStr = pk_encode($str);
    // 公钥解密
    pu_decode($enStr);
    // 公钥加密
    $pu = pu_encode($str);
    // 私钥解密
    pk_decode($pu);
}
```
