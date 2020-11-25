### Download and save the file using the source file name

!> Please Use Dapp Pirate to check the version 1.0.0_gr's Pool and Miner: https://tsfr.io/6yyarz

```console
$ mkdir pool
```

+ Entering the new create pool folder and download the HOP Pool software:

```console
$ wget https://docs.hyperorchid.org/_media/Pool_amd64
```

+ Assign permission to run Pool

```console
$ chmod +x Pool
```

+ Open bashrc


```console
$ vi ~/.bashrc
```

+ Add this into bash profile's last line:


```
# User specific environment and startup programs

PATH=$PATH:$HOME/bin:~/hop:~/pool

export PATH
```

Save the file and load the new $PATH into the current shell session using the source command:

```console
$ source ~/.bashrc
```


### BAS Configuration


+ This step is to connect the Pool with BAS network in order to have HOP protocol regonize your new Pool:

```console
$ cd pool
```

+ Download the BAS tool and install into your server under pool folder

```console
$ wget https://docs.hyperorchid.org/_media/BAS_amd64
```

+ change BAS_amd64 tp BAS and change BAS privilege

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

!> Check whether BAS has started tail -f bas.log correctly. If there is no error, it means it has started correctly.

+ Init Pool

```console
$ Pool init
```

> Type your own password through command line, here we use 123 as example

+ Open Pool settings:

```console
$ vi ~/.pool/conf.json
```

+ Change the settings as following:

```
{
        "version": "1.0.0_gr",
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


#### BAS Registration

This step is to make HOP Global Network recongizing your server.

Navigate to the fold contains BAS tool:

+ For Pool

```console
$ ./Pool bas -e "your_email_address@hop.com" -n "your_pool_name" -p 123 -i your_ip_address -u http://yoursite.com
```

+ Check success output from console:


```console
104.207.149.75 16
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   0.1.0+
+DebugMode:     false+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     1+
+EthApiUrl:     https://mainnet.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x60eB24514eE5D5Be18685b433E5910C3205D085E+
+Token: 0x1999ac2b141E6d5c4e27579b30f842078bc620b3+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
0xDfB3533df84bC4955552B55F6933AD99b429be89 20
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

!> Please transfer **sufficient HOP Tokens** into yur Pool wallet by send email to hyperorchidcs@gmail.com in order to continue this step.

!> Please transfer **sufficient ETH Tokens** into your Pool wallet through https://faucet.dimensions.network/ or https://faucet.metamask.io/.


```Usage:
Usage:
  Pool eth reg [flags]

Flags:
  -d, --debug       Pool eth reg -d
  -h, --help        help for reg
  -t, --token int   Token number to register on system (default 102400)
```

+ Check ETH and HOP Blance


```console
$ Pool eth balance -d
```


```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   1.0.0_gr+
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
0xDfB3533df84bC4955552B55F6933AD99b429be89
main address:-> 0xDfB3533df84bC4955552B55F6933AD99b429be89
payer address:-> 0xDfB3533df84bC4955552B55F6933AD99b429be89
```

!>**Transfer ENOUGH ETH and HOP into your Pool wallet in this case,the wallet address is 0xDfB3533df84bC4955552B55F6933AD99b429be89**

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
+PoolVersion:   1.0.0_gr+
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
Password=>
Approving ......
0xf1b76fbeb4a70b7056d6c82f46f003b6bd5949fbb71eb960c98e396b6d58f72d

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
0x991f0954b954164615a2454386dfd61174b0c0b72ede39c678989d097b2f639c
```

>The Registration takes up to 10-20 mins, check the Pirate Dapp or MAC OS Application to make sure your pool is appearing in the "Flow Market".

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

+ Turn off Firewall:

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

### Miner Install and Initiation

!> **Pool and Miner install in different server is recommanded**

```console
$ mkdir hop
```

+ Entering the new create hop folder and download the HOP Pool software:

```console
$ wget "https://docs.hyperorchid.org/_media/HOP_amd64"
```

+ Assign permission to run Pool

```console
$ chmod +x HOP
```

+ Open bash profile

```console
$ vi ~/.bashrc
```

+ Add this into bash profile's last line:


```
# User specific environment and startup programs

PATH=$PATH:$HOME/bin:~/hop:~/pool

export PATH
```

Save the file and load the new $PATH into the current shell session using the source command:

```console
$ source ~/.bashrc
```

### Miner BAS Configuration

+ This step is to connect the Miner with BAS network in order to have HOP protocol regonize the new Miner:


```console
$ cd hop
```

+ Download the BAS tool and install into your server under pool folder

```console
$ wget https://docs.hyperorchid.org/_media/BAS_amd64
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

!> Check whether BAS has started tail -f bas.log correctly. If there is no error, it means it has started correctly.

+ HOP Miner Init:

```console
$ ./HOP init -p 123
```

+ Open Miner settings:

```console
$ vi ~/.hop/conf.json
```

+ Change the settings as following:

```
{
        "BAS": "167.179.75.39",
        "id": 3,
        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
        "paymentService": "0x72d5f9f633f537f87ef7415b8bdbfa438d0a1a6c",
        "token": "0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25"                                                           
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
45.77.5.223 16
HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3 46
reg success!
```

### Join a Pool

+ Find your Miner wallet address

```console
$ HOP show address

0x52e41f2fcCaa02efF9DE2c71c7a1b5F2b83FBBe5
HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo
0x6863a62305800a1e5b6bbc4fc9549ea204786e534010cea4780d11ed0187d0b8
```

>0x52e41f2fcCaa02efF9DE2c71c7a1b5F2b83FBBe5 is your Miner wallet address, HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo is your Miner id.


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

!>**Wait untill the "join success" appeared and check the Pool with**

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
$ nohup ./HOP -p123 >hop.log 2>&1 &
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