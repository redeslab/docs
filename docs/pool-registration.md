### Pool Registration <!-- {docsify-ignore} -->

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