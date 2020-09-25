## 设置矿机 <!-- {docsify-ignore} -->

!>**以下的教程使用CentOS作为例子，使用Ubuntu或者类似的Linux发行版本请使用正确的命令.**


### 初始化矿机 <!-- {docsify-ignore} -->

+ 进入包含HOP可执行文件的文件夹

```console
$ HOP init -p 321
```

>使用-h选项查看帮助文档(如果遇到问题请使用-h查看更多的选项):

```console
$ HOP -h
```

+ 打开矿机配置文件:

```console
$ vi ~/.hop/conf.hop
```

+ 使用以下配置参数修改矿机配置文件:

```
{
        "version": "0.1.0",
        "basip": "34.96.151.222",
        "ethereum": {
                "1": {
                        "id": 1,
                        "apiUrl": "https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x60eB24514eE5D5Be18685b433E5910C3205D085E",
                        "token": "0x1999ac2b141E6d5c4e27579b30f842078bc620b3"
                },
                "3": {
                        "id": 3,
                        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0xF6FA41bd8f42d31a17c2343a129Fedcef2b2448d",
                        "token": "0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25"
                }
        }
}
```

!>**"id": 1为以太坊主网配置，"id": 3为Ropsten测试网络配置**