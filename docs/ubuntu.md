### Download files using Curl

!> The following steps are suitable for Ropsten testnet, for ETH mainnet please remove the option **"-d"**.

Curl can be used to transfer data over a number of protocols. It supports many protocols including HTTP, HTTPS, FTP, TFTP, TELNET, SCP, etc. using Curl, you can download any remote files. It supports pause and resumes function as well.

To get started with, first, you need to install the curl.
Install curl

Launch command line application in Ubuntu that is Terminal by pressing the Ctrl+Alt+T key combinations. Then enter the below command to install curl with sudo.

```console
$ sudo apt install curl
```

When prompted for a password, enter sudo password.


### Download and save the file using the source file name

To save the file with the same name as the original source file on the remote server, use –O (uppercase O) followed by curl as below:

```console
$ mkdir pool
```

+ Entering the new create pool folder and download the HOP Pool software:

```console
$ curl -o Pool "https://docs.hyperorchid.org/_media/Pool_amd64"
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
        "version": "0.1.0",
        "basip": "198.13.44.159",
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

!>**id 1 is for the ETH Mainnet and id 3 is for the Ropsten Testnet**

### BAS Configuration


+ This step is to connect the Pool with BAS network in order to have HOP protocol regonize your new Pool:

```console
$ sudo apt-get update -y
```

```console
$ sudo apt-get install -y net-tools
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

+ Type your password and check success output from console:


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
0xa353A767087D9aCab17c3fD941eeD29e166A9982 20
reg success!
```

> 0xa353A767087D9aCab17c3fD941eeD29e166A9982 is your Pool Ropsten ETH wallet address

#### Check BAS registration

This step uses BAS net-tool please go to docs.hyperorchid.org download the BAS for MACOS or Windows.

Navigate to the fold contains BAS tool:

+ For Pool

  BAS Hong Kong:

```console
$ BAS query -a 0xaaab(Your Pool wallet address)-b 34.96.151.222 -t1
```

  BAS JP:

```console
$ BAS query -a 0xaaab(Your Pool wallet address)-b 198.13.44.159 -t1
```


+ For Miner

  BAS Hong Kong:

```console
$ BAS query -a HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3(Your Miner ID) -b 34.96.151.222 -t2
```

  BAS JP:

```console
$ BAS query -a HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3(Your Miner ID) -b 198.13.44.159 -t2
```


### Pool Registration

Use Metamask Chrome or Firefox extension to create Ropsten wallet https://openattestation.com/docs/appendix/ropsten-setup

!> Please transfer **sufficient HOP Tokens** into yur Pool wallet by send email to hyperorchidcs@gmail.com in order to continue this step.

!> Please transfer **sufficient ETH Tokens** into your Pool wallet through https://faucet.ropsten.be/ or https://faucet.metamask.io/.


```Usage:
Pool eth reg [flags]

Flags:
  -d, --debug             Pool eth reg -d
  -e, --email string      Email address for user to contract
  -h, --help              help for reg
  -n, --name string       Pool's name to show'
  -p, --password string   Pool's account password'
  -t, --token int         Token number to register on system (default 102400)
  -u, --url string        Pool's website '
```

+ Check ETH and HOP Blance


```console
$ Pool eth balance -d
```


```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   0.1.0+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success
0xa353A767087D9aCab17c3fD941eeD29e166A9982
main address:-> 0x0000000000000000000000000000000000000000
payer address:-> 0x0000000000000000000000000000000000000000
guaranteed token:-> 0
official web:->
pool's name:->
pool's email:->
hop balance:-> 200001000000000000000000
eth balance:-> 5000000000000000000
contract approved:-> 0
```

!>**Transfer ENOUGH ETH and HOP into your Pool wallet in this case,the wallet address is 0xa353A767087D9aCab17c3fD941eeD29e166A9982**

+ Register Your Pool with Ropsten Test Network

```console
$ Pool eth reg -d -e "youremail@address.com" -n "Pool_Name" -u "https://yoursite.com"
```

+ Type your password which is created during the initiation 

```console
log init success
Password=>
```

```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   0.1.0+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
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

<a href='https://play.google.com/store/apps/details?id=com.hop.pirate&pcampaignid=pcampaignidMKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1' style="width:135px;height:40px;display: inline-block;"><img alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png'/></a>


<a href="https://apps.apple.com/us/app/%E6%B5%B7%E7%9B%97vn/id1521121265?mt=8" style="display:inline-block;overflow:hidden;background:url(https://linkmaker.itunes.apple.com/en-us/badge-lrg.svg?releaseDate=2020-07-20&kind=iossoftware&bubble=apple_music) no-repeat;width:135px;height:40px;"></a>

<a href="https://a0a63d65-7b07-4b71-9ec7-808d96916969.usrfiles.com/archives/a0a63d_7316ae011f0e4770878192986ab1d832.zip">Mac OS</a>

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

!>**Open 3000-65535 TCP and UDP port**


+ Start Pool

```console
$ Pool -d
```

```console
conf init success

++++++++++++++++++++++++++++++++++++++++++++++++++++
+PoolVersion:   0.1.0+
+DebugMode:     true+
+LogLevel:      INFO+
+Token:
++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/f3245cef90ed440897e43efc6b3dd0f7+
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++
+
++++++++++++++++++++++++++++++++++++++++++++++++++++

log init success

>>>05-08/03:15:04 mchain.go:104        newChain             [NOTI] Create micro chain sync worker success..[user version:0]..[miner version:0]..


>>>>>>>>>>miner pool start at pid(10823)<<<<<<<<<<

>>>05-08/03:15:18 mchain.go:142        Syncing              [NOTI] Miner data start to sync:sys:23 local:0

>>>05-08/03:15:18 mchain.go:151        Syncing              [NOTI] sync user account (block:508, local:0)

>>>05-08/03:18:22 mchain.go:142        Syncing              [NOTI] Miner data start to sync:sys:24 local:23
```

+ Stop Pool(We will restart Pool in next step with nohup command):

```
CTRL+C 
```

+ Restart Pool with nohup command:


```console
$ nohup Pool -d -p 123 2>pool.log &
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
$ netstat -tulpn | grep LISTEN
```

### Miner Install and Initiation

!> **Pool and Miner install in different server is recommanded**

```console
$ mkdir hop
```

+ Entering the new create hop folder and download the HOP Pool software:

```console
$ curl -o HOP "https://docs.hyperorchid.org/_media/HOP_amd64"
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
$ sudo apt-get update -y
```

```console
$ sudo apt-get install -y net-tools
```

+ HOP Miner Init:

```console
$ HOP init
```

+ Open Miner settings:

```console
$ vi ~/.hop/conf.hop
```

+ Change the settings as following:

```
{
        "BAS": "198.13.44.159",
        "id": 3,
        "apiUrl": "https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20",
        "paymentService": "0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e",
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
$ HOP bas -b 34.96.151.222 -m YOURIPADDRESS -p 321
```

AND

```console
$ HOP bas -b 198.13.44.159 -m YOURIPADDRESS -p 321
```

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
$ Pool eth join -d -s HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo -z "US_San1" -p 123
```

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
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
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
@@PayerAddr:    0xa353A767087D9aCab17c3fD941eeD29e166A9982
@@SubAddr       HO82VXn1vnBfLKC6Mx92AKk2kJPJbv4mK2YJTKBWqNWKzo
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

### Running Miner

!>**Open 3000-65535 TCP,UDP**

+ Warning up Miner

```console
$ HOP
```

Output:

```console
++++++++++++++++++++++++++++++++++++++++++++++++++++
+WalletPath:    /root/.hop/wallet.json+
+DBPath:        /root/.hop/Receipts+
+LogPath:       /root/.hop/log.hop+
+PidPath:       /root/.hop/pid.hop+
+ConfPath:      /root/.hop/conf.hop+
++++++++++++++++++++++++++++++++++++++++++++++++++++


++++++++++++++++++++++++++++++++++++++++++++++++++++
+NetworkID:     3+
+EthApiUrl:     https://ropsten.infura.io/v3/d64d364124684359ace20feae1f9ac20+
+MicroPaySys:   0x4291d9Ff189D90Ba875E0fc1Da4D602406DD7D6e+
+Token: 0xAd44c8493dE3FE2B070f33927A315b50Da9a0e25+
++++++++++++++++++++++++++++++++++++++++++++++++++++

Password=>
log init success

>>>09-13/04:36:54 micChain.go:55       newChain             [NOTI] Sync miner data:
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xa353A767087D9aCab17c3fD941eeD29e166A9982
@@SubAddr       HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

>>>>>>>>>>miner start at pid(2692)<<<<<<<<<<
```

+ Output from Pool.log

```console
>>>09-13/04:35:08 miner.go:30          updateMinerData      [NOTI] update local miner data by :
@@@@@@@@@@@@@@@@@@@@@@[Miner Data Message]@@@@@@@@@@@@@@@@@@@@@@@
@@PayerAddr:    0xa353A767087D9aCab17c3fD941eeD29e166A9982
@@SubAddr       HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3
@@GTN           50000000000000000000000
@@Zone          US
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

>>>09-13/04:36:49 mchain.go:234        newRcpReader         [DEBU] RCP Keep Alive : 0xb19b231Ea69B5A2113F09Ad9AAEa0A471272140b 187.252.197.14:51569

>>>09-13/04:36:54 receipt.go:80        createMinerRcpWire   [NOTI] New Miner online:
----------------------ReceiptQuery-----------------------
Typ:    1
UserAddr:       HO7oRHWDHXZsb8WZyENSJyceY5CiviVmJ7pRQHXEqbbQR3
PoolAddr:       0xa353A767087D9aCab17c3fD941eeD29e166A9982
-----------------~~__-__-_-_-___--___-___~~------------------
```

+ Stop Miner(We will restart Miner in next step with nohup command):

```
CTRL+C 
```

+ Running Miner with nohup:

```console
$ nohup HOP -p 321 2>hop.log &
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
$ netstat -tulpn | grep LISTEN
```

> Check Pirate Dapp to buy data from BitVPN_Ubuntu pool and enjoy the free network.