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
        "BAS": "198.13.44.159",
        "id": 3,
        "apiUrl": "https://ropsten.infura.io/v3/fe5ffffba0bf46bb9dc27fd5e04cd6cb",
        "paymentService": "0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e",
        "token": "0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25"
}
```

!>**"id": 1为以太坊主网配置，"id": 3为Ropsten测试网络配置**