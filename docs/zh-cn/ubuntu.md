### 下载和安装Pool

```console
$ mkdir pool
```

+ 进入新建的文件夹并且下载HOP Pool:

```console
$ wget https://docs.hyperorchid.org/_media/Pool_amd64
```

+ 添加Pool的可执行权限

```console
$ chmod +x Pool
```

+ 打开bashrc


```console
$ vi ~/.bashrc
```

+ 添加以下的信息到bashrc文件的最后一段:


```
# User specific environment and startup programs

PATH=$PATH:$HOME/bin:~/hop:~/pool

export PATH
```

重新加载bashrc文件让系统能辨识Pool命令：

```console
$ source ~/.bashrc
```

+ 初始化Pool

```console
$ Pool init
```

> 在命令行里面输入你想设置的密码，这里我们用123作为例子

+ 打开Pool配置文件:

```console
$ vi ~/.pool/conf.json
```

+ 用以下信息修改配置文件:

```
{
        "version": "0.1.3",
        "basip": "198.13.44.159",
        "web_port": 19576,
        "ethereum": {
                "1": {
                        "id": 1,
                        "apiUrl": "https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x60eb24514ee5d5be18685b433e5910c3205d085e",
                        "token": "0x1999ac2b141e6d5c4e27579b30f842078bc620b3"
                },
                "3": {
                        "id": 3,
                        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x4291d9ff189d90ba875e0fc1da4d602406dd7d6e",
                        "token": "0xad44c8493de3fe2b070f33927a315b50da9a0e25"
                }
        },
        "access_pub_key": [
                "0x52B65e5a662D330f259f4161Efb2eF4034365914"
        ]
}
```

!>**id 1是以太主网，id 3是Ropsten测试网**

### 添加Pool的IP到HOP全球网络中


+ 这一步是为了让HOP全球网络能识别你的新矿池:

```console
$ sudo apt-get update -y
```

```console
$ sudo apt-get install -y net-tools
```


+ 查看你的公网IP地址:

```console
$ ifconfig
```

+ 注册你的Pool到HOP全球网络，我们使用123作为示例密码:


```console
$ Pool bas -b 198.13.44.159 -i YOURIPADDRESS -p 123
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
0xa353A767087D9aCab17c3fD941eeD29e166A9982 20
reg success!
```

> 0xa353A767087D9aCab17c3fD941eeD29e166A9982是你矿池的Ropsten钱包地址

#### 查看HOP全球网络注册信息

这一步使用了BAS软件，请到docs.hyperorchid.org下载该软件.

进入包含BAS的文件夹:

+ 查看Pool

  BAS香港:

```console
$ BAS query -a 0xaaab(Your Pool wallet address)-b 34.96.151.222 -t1
```

  BAS日本:

```console
$ BAS query -a 0xaaab(Your Pool wallet address)-b 198.13.44.159 -t1
```


+ 查看矿机

  BAS香港:

```console
$ BAS query -a HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3(Your Miner ID) -b 34.96.151.222 -t2
```

  BAS日本:

```console
$ BAS query -a HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3(Your Miner ID) -b 198.13.44.159 -t2
```


### 注册Pool

使用Metamask谷歌或者火狐插件创建Ropsten钱包 https://openattestation.com/docs/appendix/ropsten-setup

!> 请转入**足够的HOP**到你的Pool钱包地址,请发送电子邮件到 hyperorchidcs@gmail.com 申请HOP测试币以便完成以下步骤.

!> 请转入**足够的ETH测试币**到Pool地址，打开 https://faucet.dimensions.network/ 或者 https://faucet.metamask.io/ 申请ETH测试币.


```Usage:
Pool eth reg [flags]

Flags:
  -d, --debug             Pool eth reg -d
  -e, --email string      Email address for user to contract
  -h, --help              help for reg
  -n, --name string       Pool's name to show'
  -p, --password string   Pool's account password'
  -t, --token int         Token number to register on system (default 102400)
  -u, --url string        Pool's website '
```

+ 查看ETH和HOP的余额


```console
$ Pool eth balance -d
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
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
0xa353A767087D9aCab17c3fD941eeD29e166A9982
main address:-> 0x0000000000000000000000000000000000000000
payer address:-> 0x0000000000000000000000000000000000000000
guaranteed token:-> 0
official web:->
pool's name:->
pool's email:->
hop balance:-> 200001000000000000000000
eth balance:-> 5000000000000000000
contract approved:-> 0
```

!>**请一定要转入足够的HOP和ETH测试币,此示例中的Pool钱包地址是 0xa353A767087D9aCab17c3fD941eeD29e166A9982**

+ 注册Pool到Ropsten测试网

```console
$ Pool eth reg -d -e "youremail@address.com" -n "Pool_Name" -u "https://yoursite.com"
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
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
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
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Approve success......
registering......
register success
0x991f0954b954164615a2454386dfd61174b0c0b72ede39c678989d097b2f639c
```

>注册矿池可能需要10-20分钟, 查看海盗Dapp或者MACOS的客户端确认你的矿池是否出现在"矿池"或者“流量市场”.

### 下载海盗以便确认你的矿池是否注册成功

海盗是一款接入HOP协议的跨平台Dapp(去中心化app). 海盗是第一款HOP的第三方合作软件. 

<a href='https://play.google.com/store/apps/details?id=com.hop.pirate&pcampaignid=pcampaignidMKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1' style="width:135px;height:40px;display: inline-block;"><img alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png'/></a>


<a href="https://apps.apple.com/us/app/%E6%B5%B7%E7%9B%97vn/id1521121265?mt=8" style="display:inline-block;overflow:hidden;background:url(https://linkmaker.itunes.apple.com/en-us/badge-lrg.svg?releaseDate=2020-07-20&kind=iossoftware&bubble=apple_music) no-repeat;width:135px;height:40px;"></a>

<a href="https://a0a63d65-7b07-4b71-9ec7-808d96916969.usrfiles.com/archives/a0a63d_7316ae011f0e4770878192986ab1d832.zip">Mac OS</a>

+ BitVPN_Ubuntu矿池已经注册成功

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

!>**打开3000-65535的TCP和UDP端口,打开BAS端口tcp：8854和udp: 8853**


+ 运行矿池

```console
$ Pool -d
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
+EthApiUrl:     https://ropsten.infura.io/v3/f3245cef90ed440897e43efc6b3dd0f7+
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success

>>>05-08/03:15:04 mchain.go:104        newChain             [NOTI] Create micro chain sync worker success..[user version:0]..[miner version:0]..


>>>>>>>>>>miner pool start at pid(10823)<<<<<<<<<<

>>>05-08/03:15:18 mchain.go:142        Syncing              [NOTI] Miner data start to sync:sys:23 local:0

>>>05-08/03:15:18 mchain.go:151        Syncing              [NOTI] sync user account (block:508, local:0)

>>>05-08/03:18:22 mchain.go:142        Syncing              [NOTI] Miner data start to sync:sys:24 local:23
```

+ 停止矿池(我们会在下一步中使用nohup命令后台运行矿池):

```
CTRL+C 
```

+ 使用nohup重启矿池:


```console
$ nohup Pool -d -p 123 2>pool.log &
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

### 矿机安装及初始化

!> **推荐矿池和矿机安装在不同的服务器上**

```console
$ mkdir hop
```

+ 进入新建的hop文件夹并且下载矿机软件:

```console
$ wget "https://docs.hyperorchid.org/_media/HOP_amd64"
```

+ 给矿机软件添加可执行权限

```console
$ chmod +x HOP
```

+ 打开bash文件

```console
$ vi ~/.bashrc
```

+ 添加以下的信息到bash文件的最后一段:


```
# User specific environment and startup programs

PATH=$PATH:$HOME/bin:~/hop:~/pool

export PATH
```

重新加载bash文件

```console
$ source ~/.bashrc
```

### 矿机全球网络设置

+ 这一步是让HOP全球网络能发现你的矿机:

```console
$ sudo apt-get update -y
```

```console
$ sudo apt-get install -y net-tools
```

+ 矿机初始化:

```console
$ HOP init
```

+ 打开矿机配置文件:

```console
$ vi ~/.hop/conf.hop
```

+ 覆盖以下信息到矿机配置文件:

```
{
        "BAS": "198.13.44.159",
        "id": 3,
        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
        "paymentService": "0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e",
        "token": "0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25"                                                           
}
```

!>**id 1是以太坊主网id 3是Ropsten测试网**


+ 查看你的公网IP地址:

```console
$ ifconfig
```

+ 注册你的矿机到HOP全球网络，这里我们使用123作为示例密码:

```console
$ HOP bas -b 198.13.44.159 -m YOURIPADDRESS -p 321
```


+ 查看命令行提示:

```
45.77.5.223 16
HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3 46
reg success!
```

### 加入矿机到一个矿池里面

+ 查看矿机钱包地址和ID

```console
$ HOP show address

0x52e41f2fcCaa02efF9DE2c71c7a1b5F2b83FBBe5
HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo
0x6863a62305800a1e5b6bbc4fc9549ea204786e534010cea4780d11ed0187d0b8
```

>0x52e41f2fcCaa02efF9DE2c71c7a1b5F2b83FBBe5是钱包地址, HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo是矿机id.


#### - 打开矿池服务器的命令行

+ 加入矿机到该矿池

```console
$ Pool eth join -d -s HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo -z "US_San1" -p 123
```

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
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
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
@@PayerAddr:    0xa353A767087D9aCab17c3fD941eeD29e166A9982
@@SubAddr       HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

### 运行矿机

!>**打开3000-65535 TCP和UDP的端口，打开BAS端口tcp：8854和udp: 8853**

+ 第一次运行矿机

```console
$ HOP
```

命令行提示:

```console
++++++++++++++++++++++++++++++++++++++++++++++++++++
+WalletPath:    /root/.hop/wallet.json+
+DBPath:        /root/.hop/Receipts+
+LogPath:       /root/.hop/log.hop+
+PidPath:       /root/.hop/pid.hop+
+ConfPath:      /root/.hop/conf.hop+
++++++++++++++++++++++++++++++++++++++++++++++++++++


++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++

Password=>
log init success

>>>09-13/04:36:54 micChain.go:55       newChain             [NOTI] Sync miner data:
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xa353A767087D9aCab17c3fD941eeD29e166A9982
@@SubAddr       HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

>>>>>>>>>>miner start at pid(2692)<<<<<<<<<<
```

+ 矿池Pool.log提示

```console
>>>09-13/04:35:08 miner.go:30          updateMinerData      [NOTI] update local miner data by :
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xa353A767087D9aCab17c3fD941eeD29e166A9982
@@SubAddr       HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

>>>09-13/04:36:49 mchain.go:234        newRcpReader         [DEBU] RCP Keep Alive : 0xb19b231Ea69B5A2113F09Ad9AAEa0A471272140b 187.252.197.14:51569

>>>09-13/04:36:54 receipt.go:80        createMinerRcpWire   [NOTI] New Miner online:
----------------------ReceiptQuery-----------------------
Typ:    1
UserAddr:       HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3
PoolAddr:       0xa353A767087D9aCab17c3fD941eeD29e166A9982
-----------------~~__-__-_-_-___--___-___~~------------------
```

+ 停止矿机(我们会在下一步用nohup重新启动矿机):

```
CTRL+C 
```

+ 用nohup命令在后台运行矿机:

```console
$ nohup HOP -p 321 2>hop.log &
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
$ nnetstat -nlp| grep HOP
```

> Check Pirate Dapp to buy data from BitVPN_Ubuntu pool and enjoy the free network.