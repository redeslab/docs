## Miner Configuration <!-- {docsify-ignore} -->

!>**This steps are for CentOS if you install Pool in Ubuntu please use the console command accordingly.**


### Initiation <!-- {docsify-ignore} -->

+ Entering the folder that contain the HOP file

```console
$ HOP init -p 321
```

>Check the help command to see more option(Please use -h option in any steps to check more options):

```console
$ HOP -h
```

+ Open Miner settings:

```console
$ vi ~/.hop/conf.hop
```

+ Change the settings as following:

```
{
        "BAS": "34.96.151.222",
        "id": 3,
        "apiUrl": "https://ropsten.infura.io/v3/fe5ffffba0bf46bb9dc27fd5e04cd6cb",
        "paymentService": "0xF6FA41bd8f42d31a17c2343a129Fedcef2b2448d",
        "token": "0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25"
}
```