

### Join a Pool <!-- {docsify-ignore} -->

+ Find your Miner wallet address

```console
$ HOP show address

0x992beCAaFA3A50A6C160624C664D3Ac792e3B4fC
HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx
0x3dc834887a192c5560a0ab1fbc8e7eeb13a5e46f9d30da09daab6c72b4166bb5
```

>0x992beCAaFA3A50A6C160624C664D3Ac792e3B4fC is your Miner wallet address, HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx is your Miner id.


#### - Open Your Pool Console

+ Join Miner to a Pool

```console
$ ./Pool eth join -p 123 -s HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo -t 30
```
Ropsten Test Network

```console
$ ./Pool eth join -d -p 123 -s HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo -t 30
```

!>**Wait untill the "join success" appeared and check the Pool with**

+ Check pool.log

```console
$ tail -f pool.log
```

Output:
```console
>>>07-14/02:05:00 miner.go:30          updateMinerData      [NOTI] update local miner data by :
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54
@@SubAddr       HO5AAw4TqjYwJsfrM5KPQdSRGgodvjk3Xghe3jNbK7Nqgx
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```
