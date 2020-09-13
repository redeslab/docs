### BAS Configuration <!-- {docsify-ignore} -->

+ This step is to connect the Miner with BAS network in order to have HOP protocol regonize the new Miner:

```console
$ yum install net-tools -y
```

+ Find your public IP address:

```console
$ ifconfig
```

+ Open Miner settings:

```console
$ vi ~/.hop/conf.hop
```

+ Change the settings as following:

```
{
        "BAS": "34.96.151.222",                                                                                                 "id": 3,
        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",                                              "paymentService": "0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e",                                                         "token": "0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25"                                                           
}
```

!>**id 1 is for the ETH Mainnet and id 3 is for the Ropsten Test network**

+ Register your Miner with BAS network, we use the 321 as password we create earlier:

```console
$ HOP bas -b 34.96.151.222 -m YOURIPADDRESS -p 321
```

