### BAS Configuration <!-- {docsify-ignore} -->


+ This step is to connect the Pool with BAS network in order to have HOP protocol regonize your new Pool:

```console
$ yum install net-tools -y
```

+ Find your public IP address:

```console
$ ifconfig
```

+ Register your Pool with BAS network, we use the 123 as password we create earlier:

```console
$ Pool bas -b 34.96.151.222 -i YOURIPADDRESS -p 123
```

AND

```console
$ Pool bas -b 198.13.44.159 -i YOURIPADDRESS -p 123
```

+ Check success output from console:

```console
...
...
...
log init success
0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54 20
reg success!
```

> 0xf8354ACf5864B88Bebf30Ea2a82b5BA05B3e8C54 is your Pool ETH wallet address