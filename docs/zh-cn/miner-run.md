
### 运行矿机 <!-- {docsify-ignore} -->

!>**打开3000以上的TCP和UDP端口**

+ 启动矿机

```console
$ HOP
```

命令行提示:

```console
>>>07-14/02:06:00 micChain.go:55       newChain             [NOTI] Sync miner data: 
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54
@@SubAddr       HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

+ 矿池服务器Pool.log日志的提示:

```console
>>>07-14/02:06:00 receipt.go:109       createMinerRcpWire   [NOTI] New Miner online:
----------------------ReceiptQuery-----------------------
Typ:    1
UserAddr:       HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx
PoolAddr:       0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54
-----------------~~__-__-_-_-___--___-___~~------------------
```

+ 停止运行矿机（下一步会使用nohup命令重启矿机）:

```
CTRL+C 
```

+ 使用nohup启动矿机:

```console
$ nohup HOP -p 321 2>hop.log &
```

+ 确认矿机运行正常:

```console
$ ps -ef|grep HOP
```

确认命令行提示HOP已经在运行:

```console
hyperor+ 14763 14586  0 03:41 pts/0    00:00:00 grep --color=auto HOP
hyperor+ 26593     1  0 Jul14 ?        00:28:13 HOP -p 321
```