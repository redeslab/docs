### Pool's Command and Option <!-- {docsify-ignore} -->

!>**Use Option -d for Ropsten Test Network**

### Pool
```console
$ ./Pool -h
```

```
Usage:
  Pool [flags]
  Pool [command]

Available Commands:
  bas             bas reg ip and block chain address
  eth             operate with ethereum contract
  help            Help about any command
  init            init miner pool
  show            show system settings
  web-access-addr show web access address

Flags:
  -d, --debug             Pool -d
  -h, --help              help for Pool
  -p, --password string   Pool -p [PASSWORD]
  -v, --version           Pool -v
```


### bas
```console
$ ./Pool bas -h
```

```
Usage:
  Pool bas [flags]

Flags:
  -b, --bas string        BAS IP to save and query, default from conf file
  -e, --email string      email for contacting pool's administrator
  -h, --help              help for bas
  -n, --name string       pool name
  -p, --password string   Pool's block chain password'
  -i, --pool-ip string    Pool's ip for it's block chain address
  -u, --url string        website address for pool
```

### eth
```console
$ ./Pool eth -h
```

```
Usage:
  Pool eth [command]

Available Commands:
  balance            show current pool's basic block chain infos
  claim              claim user's token to pool's account
  convert            convert go string to bytes type of ethereum
  export             export pool wallet to ethereum wallet
  gas                estimate transfer eth or token gas
  import-private-key import private-key
  join               make miner join the pool
  private-key        show private-key
  reg                register this pool to micro payment system
  transfer           transfer eth to other account
  transfer-token     transfer hop to other account
  unjoin             miner exit the pool
  unreg              unregister pool from micro payment channel

Flags:
  -h, --help   help for eth
```

#### eth balance

```console
$ ./Pool eth balance -h
```

```
Usage:
  Pool eth balance [flags]

Flags:
  -a, --address string   Show [ADDRESS]'s balance
  -d, --debug            Show pool's balance
  -h, --help             help for balance
```

#### eth claim

```console
$ ./Pool eth claim -h
```

```
Usage:
  Pool eth claim [flags]

Flags:
  -d, --debug                Debug model
  -h, --help                 help for claim
  -p, --password string      Pool's account password'
  -u, --userAddress string   User's address to be claimed
```

#### eth convert

```console
$ ./Pool eth convert -h
```

```
Usage:
  Pool eth convert [flags]

Flags:
  -h, --help         help for convert
  -s, --str string   Convert string to ethereum abi packed code
```

#### eth export

```console
$ ./Pool eth export -h
```

```
Usage:
  Pool eth export [flags]

Flags:
  -e, --exportPass string   Password for exported ethereum key store file
  -f, --file string         File name for exported ethereum key store (default "~/eth.wallet")
  -h, --help                help for export
  -p, --password string     Password of pool's account
```

#### eth join

```console
$ ./Pool eth join -h
```

```
Usage:
  Pool eth join [flags]

Flags:
  -d, --debug             register this pool to test network
  -h, --help              help for join
  -p, --password string   Pool's account password'
  -s, --subAddr string    Miner's sub address
  -t, --token int         Token number to join pool for miner (default 50000)
```

#### eth reg

```console
$ ./Pool eth reg -h
```

```
Usage:
  Pool eth reg [flags]
Flags:
  -d, --debug       Pool eth reg -d
  -h, --help        help for reg
  -t, --token int   Token number to register on system (default 102400)
```

#### eth unjoin

```console
$ ./Pool eth unjoin -h
```

```
Usage:
  Pool eth unjoin [flags]

Flags:
  -d, --debug             register this pool to test network
  -h, --help              help for unjoin
  -p, --password string   Pool's account password'
  -s, --subAddr string    Miner's sub address
```

#### eth unreg

```console
$ ./Pool eth unreg -h
```

```
Usage:
  Pool eth unreg [flags]

Flags:
  -d, --debug             Debug model
  -h, --help              help for unreg
  -p, --password string   Pool's account password'
```

### init

```console
$ ./Pool init -h
```

```
Usage:
  Pool init [flags]

Flags:
  -h, --help              help for init
  -p, --password string   Password to init pool
```

### show

```console
$ ./Pool show -h
```

```
Usage:
  Pool show [command]

Available Commands:
  address     show wallet main address
  allminer    show all miner data
  alluser     show all user data
  conf        show system configuration address
  income      show all income
  miner       show miner info data
  pool        show all pool
  receipt     show lasted receipt
  subpool     show subscribe pool
  user        show local user account data

Flags:
  -h, --help   help for show
```

#### show address

```console
$ ./Pool show address -h
```

```
Usage:
  Pool show address [flags]

Flags:
  -h, --help   help for address
```

#### show conf

```console
$ ./Pool show conf -h
```

```
Usage:
  Pool show conf [flags]

Flags:
  -h, --help   help for conf
```

#### show miner

```console
$ ./Pool show miner -h
```

```
Usage:
  Pool show miner [flags]

Flags:
  -h, --help           help for miner
  -m, --miner string   Miner's block chain password'
```

#### - show receipt

```console
$ ./Pool show receipt -h
```

```
Usage:
  Pool show receipt [flags]

Flags:
  -h, --help          help for receipt
  -u, --user string   User's block chain password'
```

#### show user

```console
$ ./Pool show user -h
```

```
Usage:
  Pool show user [flags]

Flags:
  -h, --help          help for user
  -u, --user string   User's block chain password'
```

