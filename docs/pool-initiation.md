## Pool Configuration <!-- {docsify-ignore} -->

!>**This steps are for CentOS if you install Pool in Ubuntu please use the console command accordingly.**


### Initiation


+ Entering the folder that contain the Pool file

```console
$ Pool init -p 123
```

>Check the help command to see more option(Please use -h option in any steps to check more options):

```console
$ Pool -h
```

+ Open Pool settings:

```console
$ vi ~/.pool/conf.json
```

+ Change the settings as following:

```
{
        "version": "0.1.0",
        "basip": "34.96.151.222",
        "ethereum": {
                "1": {
                        "id": 1,
                        "apiUrl": "https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x60eB24514eE5D5Be18685b433E5910C3205D085E",
                        "token": "0x1999ac2b141E6d5c4e27579b30f842078bc620b3"
                },
                "3": {
                        "id": 3,
                        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e",
                        "token": "0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25"
                }
        }
}
```

!>**id 1 is for the ETH Mainnet and id 3 is for the Ropsten Test network**