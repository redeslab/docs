### 设置BAS <!-- {docsify-ignore} -->


+ 这一步的目的是为了让矿池连接BAS网络并且让HOP协议接受你的新矿池:

+ 安装网络工具包

```console
$ yum install net-tools -y
```

+ 查看你的IP地址:

```console
$ ifconfig
```

+ 在BAS网络里注册你的矿池, 我们使用之前设置的123做为密码:

```console
$ Pool bas -i YOURIPADDRESS -p 123
```

+ 查看设置成功的命令行提示:

```console
...
...
...
log init success
0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54 20
reg success!
```

> 0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54 是你的以太坊钱包公钥地址。