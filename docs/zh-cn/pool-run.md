
### 运行矿池 <!-- {docsify-ignore} -->

+ 关闭防火墙:

```console
systemctl stop firewalld.service 
systemctl disable firewalld.service
```

!>**打开3000以上的TCP和UDP端口**

+ 开启矿池

```console
$ Pool 
```

Ropsten测试网络

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

+ 关闭矿池（下一步会使用nohup命令重启矿池）:

```
CTRL+C 
```

+ 使用nohup命令重启矿池，并且把日志写入pool.log文件:

```console
$ nohup Pool -p 123 2>pool.log &
```

Ropsten测试网络

```console
$ nohup Pool -d -p 123 2>pool.log &
```

+ 确认矿池运行正常:

```console
$ ps -ef|grep Pool
```

确认命令行提示Pool已经在运行:

```
hyperor+  9470  9437  0 23:07 pts/0    00:00:00 grep --color=auto Pool
hyperor+ 23592     1  0 Jul09 ?        00:32:34 Pool -d -p 123
```