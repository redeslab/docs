### 设置BAS <!-- {docsify-ignore} -->

+ 这一步的目的是为了让矿机连接BAS网络并且让HOP协议接受你的新矿机:

```console
$ yum install net-tools -y
```

+ 查看你的公网IP地址:

```console
$ ifconfig
```


+ 在BAS网络里注册你的矿机, 我们使用之前设置的321做为密码:


```console
$ HOP bas -b 34.96.151.222 -m YOURIPADDRESS -p 321
```

AND

```console
$ HOP bas -b 198.13.44.159 -m YOURIPADDRESS -p 321
```
