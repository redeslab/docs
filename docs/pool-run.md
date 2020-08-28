
### Running Pool <!-- {docsify-ignore} -->

+ Turn off Firewall:

```console
systemctl stop firewalld.service 
systemctl disable firewalld.service
```

+ Start Pool

```console
$ Pool 
```

Ropsten Test Network

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

+ Stop Pool:

```
CTRL+C 
```

+ Restart Pool with nohup command:

```console
$ nohup Pool -p 123 2>pool.log &
```

Ropsten Test Network

```console
$ nohup Pool -d -p 123 2>pool.log &
```
