
### Running Pool <!-- {docsify-ignore} -->

+ Turn off Firewall(Optional):

```console
systemctl stop firewalld.service 
systemctl disable firewalld.service
```

!>**Open 3000-65535 TCP and UDP port and BAS tcp：8854 udp: 8853**


+ Start Pool

```console
$ nohup ./Pool -d -p123> pool.log 2>&1 &
```


+ Make sure the Pool is running

```console
$ ps -ef|grep Pool
```

Output:

```
hyperor+  9470  9437  0 23:07 pts/0    00:00:00 grep --color=auto Pool
hyperor+ 23592     1  0 Jul09 ?        00:32:34 Pool -d -p 123
```

+ Check ports Pool are using if you have problem register the Pool and open the ports if they are closed:

```console
$ netstat -nlp| grep Pool
```