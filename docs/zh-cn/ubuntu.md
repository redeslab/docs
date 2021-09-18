### 下载和安装Pool

!> 请发邮件和你的Rinkeby测试网的钱包地址到cs@hopchain.org申请1000个HOP测试币,矿池需要300HOP抵押，矿机需要30。

!> 中文测试的APP已经发布，[安卓]https://tsfr.io/join/c2vt2r

!> 矿池和矿机不能存在于同一个网络环境，同一台机器或者同一个路由器后面。

```console
$ mkdir pool
```

+ 进入新建的文件夹并且下载HOP Pool:

```console
$ wget https://docs.hopchain.org/_media/Pool_Rinkeby_amd64
```

+ 添加Pool的可执行权限

```console
$ chmod +x Pool
```


### BAS Configuration


+ 这一步是为了让HOP全球网络能识别你的新矿池:

```console
$ cd pool
```

+ 下载BAS工具到pool文件夹

```console
$ wget https://docs.hopchain.org/_media/BAS_amd64
```

+ 改名BAS_amd64为BAS并且添加运行权限

```console
$ mv BAS_amd64 BAS
```

```console
$ chmod +x BAS
```

+ 启动BAS

```console
$ nohup ./BAS> bas.log 2>&1 &
```

!> 检查BAS是否正确启动 tail -f bas.log，日志如果没有错误，表明已经正确启动了。
!>**打开相应 TCP和UDP的端口，打开BAS端口tcp：8854和udp: 8853**



+ 初始化Pool

```console
$ ./Pool init
```

> 在命令行里面输入你想设置的密码，这里我们用123作为例子

+ 打开Pool配置文件:

```console
$ vi ~/.pool/conf.json
```

+ 用以下信息修改配置文件:

```
{
  "version": "1.1.7",
    "basip": "119.120.92.235",
    "web_port": 42888,
    "ethereum": {
      "1": {
        "id": 1,
        "apiUrl": "https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20",
        "paymentService": "0x5ec8589c8832ade0b45c608681bbacef517e7cad",
        "token": "0x1999ac2b141e6d5c4e27579b30f842078bc620b3"
      },
      "3": {
        "id": 3,
        "apiUrl": "https://rinkeby.infura.io/v3/d64d364124684359ace20feae1f9ac20",
        "paymentService": "0xb7b93d75690C4d1E8110D8D86b09Ff43BcA4335a",
        "token": "0x72F391A5fC31b026739C8C26e0c5C01b2783F786"
      }
    }
}
```

!>**id 1是以太主网，id 3是Rinkeby测试网**

### 添加Pool的IP到HOP全球网络中


+ 注册你的Pool到HOP全球网络，我们使用123作为示例密码:


```console
$ ./Pool bas -e "your_email_address@hop.com" -n "your_pool_name" -p 123 -i your_ip_address -u http://yoursite.com
```

+ 查看命令行成功的提示信息:


```console
104.207.149.75 16
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   0.1.0+
+DebugMode:     false+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     1+
+EthApiUrl:     https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x60eB24514eE5D5Be18685b433E5910C3205D085E+
+Token: 0x1999ac2b141E6d5c4e27579b30f842078bc620b3+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
0xDfB3533df84bC4955552B55F6933AD99b429be89 20
reg success!
```

> 0xDfB3533df84bC4955552B55F6933AD99b429be89是你矿池的Ropsten钱包地址

+ Pool bas命令

```Usage:
Flags:
  -b, --bas string        BAS IP to save and query, default from conf file
  -e, --email string      email for contacting pool's administrator
  -h, --help              help for bas
  -n, --name string       pool name
  -p, --password string   Pool's block chain password'
  -i, --pool-ip string    Pool's ip for it's block chain address
  -u, --url string        website address for pool
```

### 注册Pool

使用Metamask谷歌或者火狐插件创建Ropsten钱包 https://medium.com/@mail.bahurudeen/setup-a-metamask-ethereum-wallet-and-use-it-to-send-and-receive-ether-4f3b99360e4f

!> 请转入**足够的HOP**到你的Pool钱包地址,请发送电子邮件到 cs@hopchain.org 申请HOP测试币以便完成以下步骤.

!> 请转入**足够的ETH测试币**到Pool地址，打开 https://faucet.rinkeby.io/ 或者 https://rinkeby.faucet.epirus.io/ 申请ETH测试币.


```Usage:
Usage:
  Pool eth reg [flags]

Flags:
  -d, --debug       Pool eth reg -d
  -h, --help        help for reg
  -t, --token int   Token number to register on system (default 102400)
```

+ 查看ETH和HOP的余额


```console
$ ./Pool eth balance -d
```


```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   1.0.0_gr+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x72d5f9f633f537f87ef7415b8bdbfa438d0a1a6c+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
0xDfB3533df84bC4955552B55F6933AD99b429be89
main address:-> 0xDfB3533df84bC4955552B55F6933AD99b429be89
payer address:-> 0xDfB3533df84bC4955552B55F6933AD99b429be89
```

!>**请一定要转入足够的HOP和ETH测试币,此示例中的Pool钱包地址是 0xDfB3533df84bC4955552B55F6933AD99b429be89**

+ 注册Pool到Rinkeby测试网

```console
$ ./Pool eth reg -d -t 300
```

+ 输入你在初始化的步骤设置的Pool密码

```console
log init success
Password=>
```

```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   0.1.0+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x72d5f9f633f537f87ef7415b8bdbfa438d0a1a6c+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
Password=>
Approving ......
0xf1b76fbeb4a70b7056d6c82f46f003b6bd5949fbb71eb960c98e396b6d58f72d

Tx is in process: not found
Tx is in process: not found
Approve success......
registering......
register success
0x991f0954b954164615a2454386dfd61174b0c0b72ede39c678989d097b2f639c
```

>注册矿池可能需要5-10分钟, 查看海盗Dapp或者MACOS的客户端确认你的矿池是否出现在"矿池"或者“流量市场”.

### 下载流量App以便确认你的矿池是否注册成功

<!--海盗是一款接入HOP协议的跨平台Dapp(去中心化app). 海盗是第一款HOP的第三方合作软件. 

<a href='https://play.google.com/store/apps/details?id=com.hop.pirate&pcampaignid=pcampaignidMKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1' style="width:135px;height:40px;display: inline-block;"><img alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png'/></a>


<a href="https://apps.apple.com/us/app/%E6%B5%B7%E7%9B%97vn/id1521121265?mt=8" style="display:inline-block;overflow:hidden;background:url(https://linkmaker.itunes.apple.com/en-us/badge-lrg.svg?releaseDate=2020-07-20&kind=iossoftware&bubble=apple_music) no-repeat;width:135px;height:40px;"></a>

<a href="https://a0a63d65-7b07-4b71-9ec7-808d96916969.usrfiles.com/archives/a0a63d_7316ae011f0e4770878192986ab1d832.zip">Mac OS</a> 
<a href="https://tsfr.io/6yyarz">APK</a>-->

+ 矿池已经注册成功

**iOS**

![logo](_media/bitvpn_iOS_2020-09-12_17-03-22.jpg ':size=40%')

**Android**

![logo](_media/bitvpn_android_2020-09-12_17-02-31.jpg ':size=40%')


### 运行矿池

+ 关闭防火墙:

```console
systemctl stop firewalld.service 
systemctl disable firewalld.service
```


+ 运行矿池

```console
$ nohup ./Pool -d -p 123> pool.log 2>&1 &
```

+ 确认矿池已经在后台运行

```console
$ ps -ef|grep Pool
```

命令行输出:

```
hyperor+  9470  9437  0 23:07 pts/0    00:00:00 grep --color=auto Pool
hyperor+ 23592     1  0 Jul09 ?        00:32:34 Pool -d -p 123
```

+ 确认用以下命令查看矿池的端口都已经打开:

```console
$ netstat -nlp| grep Pool
```

!>**打开相应 TCP和UDP的端口，打开BAS端口tcp：8854和udp: 8853**

### 矿机安装及初始化

!> **推荐矿池和矿机安装在不同的服务器上**

```console
$ mkdir hop
```

+ 进入新建的hop文件夹并且下载矿机软件:

```console
$ wget "https://docs.hopchain.org/_media/HOP_Rinkeby_amd64"
```

+ 给矿机软件添加可执行权限

```console
$ chmod +x HOP
```

+ 矿机初始化:

```console
$ ./HOP init -p 123
```

+ 打开矿机配置文件:

```console
$ vi ~/.hop/conf.hop
```

+ 覆盖以下信息到矿机配置文件:

```
{
  "bas": "119.120.92.235",
    "ECfg": {
      "1": {
        "id": 1,
        "apiUrl": "https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20",
        "paymentService": "0x5ec8589c8832ade0b45c608681bbacef517e7cad",
        "token": "0x1999ac2b141e6d5c4e27579b30f842078bc620b3"
      },
      "3": {
        "id": 3,
        "apiUrl": "https://rinkeby.infura.io/v3/d64d364124684359ace20feae1f9ac20",
        "paymentService": "0xb7b93d75690C4d1E8110D8D86b09Ff43BcA4335a",
        "token": "0x72F391A5fC31b026739C8C26e0c5C01b2783F786"
      }
    },
    "web_port": 42887,
    "access_pub_key": null
}
```

!>**id 1是以太坊主网id 3是Ropsten测试网**


+ 查看你的公网IP地址:

```console
$ ifconfig
```

+ 注册你的矿机到HOP全球网络"minerloc"可以根据你的地点来更改，这里我们使用123作为示例密码:

```console
$ ./HOP bas -l "minerloc" -m your_miner_ip -p 321
```

其中-l表示矿机的位置信息，最多可以填入八个字节，-m表示矿机的外网服务地址。

+ 查看命令行提示:

```
45.77.5.223 16
HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3 46
reg success!
```

### 加入矿机到一个矿池里面

+ 查看矿机钱包地址和ID

```console
$ ./HOP show address

0x52e41f2fcCaa02efF9DE2c71c7a1b5F2b83FBBe5
HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo
0x6863a62305800a1e5b6bbc4fc9549ea204786e534010cea4780d11ed0187d0b8
```

>0x52e41f2fcCaa02efF9DE2c71c7a1b5F2b83FBBe5是钱包地址, HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo是矿机id.


#### - 打开矿池服务器的命令行

+ 加入矿机到该矿池

```console
$ ./Pool eth join -d -p 123 -s HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo -t 30
```
其中-s代表矿机的微支付地址，-t是指矿机需要抵押的hop币[最少30]

命令行提示

```
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   0.1.0+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x72d5f9f633f537f87ef7415b8bdbfa438d0a1a6c+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
Approving ......
0x1b182e1456462ac5cfce062dc335d53bd0a5050d1c71f43d698d0164b021c9b6

Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Approve success......
Joining pool......
join success
0x8c3e14ce536bebc2ce5b3c98faff44d199878ffbde27f20d678a37b516bb6439
```

!>**请等到"join success"出现在命令行**

+ 查看pool.log

```console
$ tail -f pool.log
```

  提示:
```console
>>>09-13/03:08:44 mchain.go:150        Syncing              [NOTI] Miner data start to sync:sys:90 local:89

>>>09-13/03:08:44 miner.go:30          updateMinerData      [NOTI] update local miner data by :
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xDfB3533df84bC4955552B55F6933AD99b429be89
@@SubAddr       HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

### 运行矿机


+ 用nohup命令在后台运行矿机:

```console
$ nohup ./HOP -d -p 321 >hop.log 2>&1 &
```

+ 查看矿机运行是否正常:

```console
$ ps -ef|grep HOP
```

命令行提示:

```console
root        2702    2681 23 04:41 pts/2    00:00:01 HOP -p 321
root        2711    2681  0 04:41 pts/2    00:00:00 grep --color=auto HOP
```

+ 使用以下命令确认所有矿机占用的端口都已经打开:

```console
$ netstat -nlp| grep HOP
```

!>**打开相应 TCP和UDP的端口，打开BAS端口tcp：8854和udp: 8853**


> 查看流量app，购买流量，享受您的网络。