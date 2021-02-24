## Pool Configuration <!-- {docsify-ignore} -->

!>**This steps are for CentOS if you install Pool in Ubuntu please use the console command accordingly.**


### Initiation


+ Init Pool

```console
$ ./Pool init
```

> Type your own password through command line, here we use 123 as example

+ Open Pool settings:

```console
$ vi ~/.pool/conf.json
```

+ Change the settings as following:

```
{
        "version": "1.0.3m_gr",
        "basip": "167.179.75.39",
        "web_port": 42888,
        "ethereum": {
                "1": {
                        "id": 1,
                        "apiUrl": "https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x60eb24514ee5d5be18685b433e5910c3205d085e",
                        "token": "0x1999ac2b141e6d5c4e27579b30f842078bc620b3"
                },
                "3": {
                        "id": 3,
                        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x72d5f9f633f537f87ef7415b8bdbfa438d0a1a6c",
                        "token": "0xad44c8493de3fe2b070f33927a315b50da9a0e25"
                }
        },
        "access_pub_key": [
                "0x52B65e5a662D330f259f4161Efb2eF4034365914"
        ]
}
```

!>**id 1 is for the ETH Mainnet and id 3 is for the Ropsten Testnet**