

### 加入矿池 <!-- {docsify-ignore} -->

+ 查看你的矿机以太坊公钥地址

```console
$ HOP show address

0x992beCAaFA3A50A6C160624C664D3Ac792e3B4fC
HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx
0x3dc834887a192c5560a0ab1fbc8e7eeb13a5e46f9d30da09daab6c72b4166bb5
```

>0x992beCAaFA3A50A6C160624C664D3Ac792e3B4fC 是你的以太坊公钥地址, HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx 是你的矿机ID.


#### - 切换到Pool服务器的命令行窗口

+ 加入到矿池

```console
$ Pool eth join -s HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx -z "US" -p 123
```
Ropsten测试网

```console
$ Pool eth join -d -s HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx -z "US" -p 123
```

!>**请等到"join success"提示出现在矿池服务器命令行窗口**

+ 查看矿池日志

```console
$ tail -f pool.log
```

+ 矿机成功加入矿池的记录:

```console
07-14/02:05:00 miner.go:30          updateMinerData      [NOTI] update local miner data by :
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54
@@SubAddr       HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```
