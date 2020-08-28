
### Running Miner <!-- {docsify-ignore} -->

+ Warning up Miner

```console
$ HOP
```

Output:

```console
>>>07-14/02:06:00 micChain.go:55       newChain             [NOTI] Sync miner data: 
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54
@@SubAddr       HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

+ Output from Pool.log

```console
>>>07-14/02:06:00 receipt.go:109       createMinerRcpWire   [NOTI] New Miner online:
----------------------ReceiptQuery-----------------------
Typ:    1
UserAddr:       HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx
PoolAddr:       0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54
-----------------~~__-__-_-_-___--___-___~~------------------
```

+ Stop Miner:

```
CTRL+C 
```

+ Running Miner with nohup:

```console
$ nohup HOP -p 321 2>hop.log &
```

+ Check Miner thread is running properly:

```console
$ ps -ef|grep HOP
```

Output:

```console
hyperor+ 14763 14586  0 03:41 pts/0    00:00:00 grep --color=auto HOP
hyperor+ 26593     1  0 Jul14 ?        00:28:13 HOP -p 321
```