### Pool Registration <!-- {docsify-ignore} -->

!> Please transfer **sufficient HOP and ETH Tokens** into your Pool wallet in order to continue this step.


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

```console
$ Pool eth reg -e "youremail@address.com" -n "Pool_Name" -u "https://yoursite.com"
```

Ropsten Test Network

```console
$ Pool eth reg -d -e "youremail@address.com" -n "Pool_Name" -u "https://yoursite.com"
```

+ Type your password which is created during the initiation 

```console
log init success
Password=>
```

```console
Approving...
...
...
Tx is in process: not found
Tx is in process: not found
Tx is in process: not found
Approve success......
registering......
```

>The Registration takes up to 10-20 mins, check the Pirate Dapp or MAC OS Application to make sure your pool is appearing in the "Flow Market".

