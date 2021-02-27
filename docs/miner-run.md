
### Running Miner <!-- {docsify-ignore} -->

!>**Open 3000-65535 TCP,UDP and BAS tcp：8854 udp: 8853**


+ Running Miner with nohup:

```console
$ nohup ./HOP -d -p 321 >hop.log 2>&1 &
```

+ Check Miner thread is running properly:

```console
$ ps -ef|grep HOP
```

Output:

```console
root        2702    2681 23 04:41 pts/2    00:00:01 HOP -p 321
root        2711    2681  0 04:41 pts/2    00:00:00 grep --color=auto HOP
```

+ To make sure which TCP and UDP ports Miner are using please use following command and open the ports that Miner needed:

```console
$ netstat -nlp| grep HOP
```

> Check Pirate Dapp to buy data from this pool and enjoy the free network.