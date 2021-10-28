### Download and save the file using the source file name

!> Please Use Dapp Pirate to check the version 1.0.3m_gr's Pool and Miner: https://piratedownload.github.io/

```console
$ mkdir pool
```

+ Entering the new create pool folder and download the HOP Pool software:

```console
$ wget https://docs.hopchain.org/_media/Pool_amd64
```

+ Assign permission to run Pool

```console
$ chmod +x Pool
```


<!--### BAS Configuration


+ This step is to connect the Pool with BAS network in order to have HOP protocol recognize your new Pool:

```console
$ cd pool
```

+ Download the BAS tool and install into your server under pool folder

```console
$ wget https://docs.hopchain.org/_media/BAS_amd64
```

+ change BAS_amd64 to BAS and change BAS privilege

```console
$ mv BAS_amd64 BAS
```

```console
$ chmod +x BAS
```

+ Start the BAS

```console
$ nohup ./BAS> bas.log 2>&1 &
```

!> Check whether BAS has started tail -f bas.log correctly. If there is no error, it means it has started correctly.-->
!>**Open 3000-65535 TCP and UDP port and BAS tcp：8854 udp: 8853**

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
  "version": "1.1.6",
  "basip": "34.92.151.100",
  "web_port": 42888,
  "ethereum": {
          "1": {
                  "id": 1,
                  "apiUrl": "https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                  "paymentService": "0x5ec8589c8832ade0b45c608681bbacef517e7cad",
                  "token": "0x1999ac2b141e6d5c4e27579b30f842078bc620b3"
          },
          "3": {
                  "id": 3,
                  "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                  "paymentService": "0x72d5f9f633f537f87ef7415b8bdbfa438d0a1a6c",
                  "token": "0xad44c8493de3fe2b070f33927a315b50da9a0e25"
          }
  },
  "access_addr": [
          "0x52B65e5a662D330f259f4161Efb2eF4034365914"
  ]
}
```

!>**id 1 is for the ETH Mainnet and id 3 is for the Ropsten Testnet**


#### BAS Registration

This step is to make HOP Global Network recognizing your server.

Navigate to the fold contains BAS tool:

+ For Pool

```console
$ ./Pool bas -e "your_email_address@hop.com" -n "your_pool_name" -p 123 -i your_ip_address -u http://yoursite.com
```

+ Check success output from console:


```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   1.0.3m_gr+
+DebugMode:     false+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     1+
+EthApiUrl:     https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x5eC8589C8832AdE0B45C608681bbaCEF517E7caD+
+Token: 0x1999ac2b141E6d5c4e27579b30f842078bc620b3+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
bas ip not set, use system setting ip
0xfd3F857b882f2Ae5D8c247605a81E1350DC7D7eB 20
reg success!
```

> 0xDfB3533df84bC4955552B55F6933AD99b429be89 is your Pool Ropsten ETH wallet address

+ Pool bas commands

```Usage:
Flags:
  -b, --bas string        BAS IP to save and query, default from conf file
  -e, --email string      email for contacting pool's administrator
  -h, --help              help for bas
  -n, --name string       pool name
  -p, --password string   Pool's block chain password'
  -i, --pool-ip string    Pool's ip for it's block chain address
  -u, --url string        website address for pool
```

### Pool Registration

Use Metamask Chrome or Firefox extension to create Ropsten wallet https://openattestation.com/docs/appendix/ropsten-setup

!> Please transfer **sufficient HOP Tokens** into your Pool wallet by send email to cs@hopchain.org in order to continue this step.

!> Please transfer **sufficient ETH Tokens** into your Pool wallet through https://faucet.dimensions.network/ or https://faucet.metamask.io/.


```Usage:
Usage:
  Pool eth reg [flags]

Flags:
  -d, --debug       Pool eth reg -d
  -h, --help        help for reg
  -t, --token int   Token number to register on system (default 102400)
```

+ Check ETH and HOP Balance


```console
$ ./Pool eth balance -d
```


```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   1.0.3m_gr+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x72D5f9f633f537F87Ef7415B8Bdbfa438D0a1a6c+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
0xfd3F857b882f2Ae5D8c247605a81E1350DC7D7eB
main address:-> 0xfd3F857b882f2Ae5D8c247605a81E1350DC7D7eB
payer address:-> 0xfd3F857b882f2Ae5D8c247605a81E1350DC7D7eB

++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x72D5f9f633f537F87Ef7415B8Bdbfa438D0a1a6c+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++

hop balance:-> 300000000000000000000
eth balance:-> 1000000000000000000
contract approved:-> 0
```

!>**Transfer ENOUGH ETH and HOP into your Pool wallet in this case,the wallet address is 0xfd3F857b882f2Ae5D8c247605a81E1350DC7D7eB**

+ Register Your Pool with Ropsten Test Network, Where -t represents the HOP value mortgaged to the contract, which must be greater than or equal to 300.

```console
$ ./Pool eth reg -d -t 300
```

+ Type your password which is created during the initiation 

```console
log init success
Password=>
```

```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   1.0.3m_gr+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x72D5f9f633f537F87Ef7415B8Bdbfa438D0a1a6c+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
Password=>
Approving ......
0x8227fc76c00b1f1c93a1d699f359762c66c5c6720cae875f7a4c08f7f88356e2

Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Approve success......
registering......
register success
0x9b36d5c6c267b709b6f15390a9e78a581e0bad6de17b10f2eca1a11ce6ffc15b
```

>The Registration takes up to 10 mins, check the Pirate Dapp or MAC OS Application to make sure your pool is appearing in the "Flow Market".

### Download Pirate and check your Pool is successfully registered or not

Pirate is a cross-platform Dapp(Decentralized Application) developed in HOP protocol. Pirate is the first affiliate software whose sole goal is to provide VPN app to all users. 

<!--<a href='https://play.google.com/store/apps/details?id=com.hop.pirate&pcampaignid=pcampaignidMKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1' style="width:135px;height:40px;display: inline-block;"><img alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png'/></a>


<a href="https://apps.apple.com/us/app/%E6%B5%B7%E7%9B%97vn/id1521121265?mt=8" style="display:inline-block;overflow:hidden;background:url(https://linkmaker.itunes.apple.com/en-us/badge-lrg.svg?releaseDate=2020-07-20&kind=iossoftware&bubble=apple_music) no-repeat;width:135px;height:40px;"></a>

<a href="https://a0a63d65-7b07-4b71-9ec7-808d96916969.usrfiles.com/archives/a0a63d_7316ae011f0e4770878192986ab1d832.zip">Mac OS</a>*-->

<a href="https://tsfr.io/6yyarz">APK</a>

+ BitVPN_Ubuntu successfully registered

**iOS**

![logo](_media/bitvpn_iOS_2020-09-12_17-03-22.jpg ':size=40%')

**Android**

![logo](_media/bitvpn_android_2020-09-12_17-02-31.jpg ':size=40%')


### Running Pool

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

+ Check ports that Pool are using when the Pool has problem to register and if the ports are blocked please open them through firewall or your cloud console:

```console
$ netstat -nlp| grep Pool
```

### Miner Install and Initiation

!> **Pool and Miner install in different server is recommanded**

```console
$ mkdir hop
```

+ Entering the new create hop folder and download the HOP Pool software:

```console
$ wget "https://docs.hopchain.org/_media/HOP_amd64"
```

+ Assign permission to run Pool

```console
$ chmod +x HOP
```

+ HOP Miner Init:

```console
$ ./HOP init -p 321
```

+ Open Miner settings:

```console
$ vi ~/.hop/conf.hop
```

+ Change the settings as following:

```
{
        "bas": "34.92.151.100",
        "ECfg": {
                "1": {
                        "id": 1,
                        "apiUrl": "https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x5ec8589c8832ade0b45c608681bbacef517e7cad",
                        "token": "0x1999ac2b141e6d5c4e27579b30f842078bc620b3"
                },
                "3": {
                        "id": 3,
                        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
                        "paymentService": "0x72d5f9f633f537f87ef7415b8bdbfa438d0a1a6c",
                        "token": "0xad44c8493de3fe2b070f33927a315b50da9a0e25"
                }
        },
        "web_port": 42887,
        "access_pub_key": null
}
```

!>**id 1 is for the ETH Mainnet and id 3 is for the Ropsten Test network**


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

### Join a Pool

+ Find your Miner wallet address

```console
$ ./HOP show address

0x077Cd0084A871DF5b5802Abcd08837a1C1118402
HO9Wk5VCnaeuNFVxhbaDAQc5ZEhe4iuz45JTYCpsjbFNZM
0x7e7c0bed340b025185ea26dc8edc3865b0bc320feb6c6266254c357f00cdb8d8
```

>0x077Cd0084A871DF5b5802Abcd08837a1C1118402 is your Miner wallet address, HO9Wk5VCnaeuNFVxhbaDAQc5ZEhe4iuz45JTYCpsjbFNZM is your Miner id.


#### - Open Your Pool Console

+ Join Miner to a Pool

```console
$ ./Pool eth join -d -p 123 -s HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo -t 30
```

>Where -s represents the micropayment address of the miner, and -t represents the hop tokens that the miner needs to deposit[minimum is 30].

Output

```
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   0.1.0+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x72d5f9f633f537f87ef7415b8bdbfa438d0a1a6c+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
Approving ......
0x1b182e1456462ac5cfce062dc335d53bd0a5050d1c71f43d698d0164b021c9b6

Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Approve success......
Joining pool......
join success
0x8c3e14ce536bebc2ce5b3c98faff44d199878ffbde27f20d678a37b516bb6439
```

!>**Wait until the "join success" appeared**

+ Check pool.log

```console
$ tail -f pool.log
```

  Output:
```console
>>>09-13/03:08:44 mchain.go:150        Syncing              [NOTI] Miner data start to sync:sys:90 local:89

>>>09-13/03:08:44 miner.go:30          updateMinerData      [NOTI] update local miner data by :
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xDfB3533df84bC4955552B55F6933AD99b429be89
@@SubAddr       HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

### Running Miner

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