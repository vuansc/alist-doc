---
sidebar_position: 19
---

# 百度网盘

:::tip
由于百度网盘API的限制，下载较大的文件（目测>20M）需要携带header："User-Agent":"pan.baidu.com"，所以在下载大于20M的文件时，需要自行设置请求头，如使用curl：
```bash
curl -L -X GET 'YOUR_LINK' -H 'User-Agent: pan.baidu.com' 
```
或使用本程序中的代理功能进行中转。
:::

### 刷新令牌
[点此](http://openapi.baidu.com/oauth/2.0/authorize?response_type=code&client_id=iYCeC9g08h5vuP9UqvPHKKSVrKFXGa1v&redirect_uri=https://tool.nn.ci/baidu/callback&scope=basic,netdisk&qrcode=1)获取刷新令牌。

### 根目录路径
要挂载的根目录，默认为`/`