### BAS Configuration <!-- {docsify-ignore} -->

+ This step is to connect the Miner with BAS network in order to have HOP protocol regonize the new Miner:

+ Find your public IP address:

```console
$ ifconfig
```

+ Register your Miner with BAS network, we use the 321 as password we create earlier:


```console
$ ./HOP bas -l "minerloc" -m your_miner_ip -p 321
```

!> where -l represents the location information of the miner, which can be filled in at most eight bytes, and -m represents the external network service ip address of the miner.


+ Check console output:

```
34.96.209.214 16
bas ip not set, use system config ip address
reg success!
```