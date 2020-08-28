### - Miner's Command and Option <!-- {docsify-ignore} -->

### HOP 

```console
$ HOP -h
```

```
Usage:
  HOP [flags]
  HOP [command]

Available Commands:
  bas         register self to block chain service
  help        Help about any command
  init        init miner node
  show        show miner's basic info

Flags:
  -b, --basIP string      Bas IP (default "108.61.223.99")
  -c, --cmdPort string    Cmd service port (default "42017")
  -h, --help              help for HOP
  -p, --password string   Password to unlock miner
  -v, --version           HOP version

Use "HOP [command] --help" for more information about a command.
```

### bas

```console
$ HOP bas -h
```

```
Usage:
  HOP bas [flags]

Flags:
  -b, --basIP string      HOP bas -b [BAS IP]] (default "108.61.223.99")
  -h, --help              help for bas
  -m, --minerIP string    HOP bas -m [MY IP Address]
  -p, --password string   HOP bas -p [PASSWORD]
```

### init

```console
$ HOP init -h
```

```
Usage:
  HOP init [flags]

Flags:
  -h, --help              help for init
  -p, --password string   Password to create Hyper Orchid block chain system.
```

### show

```console
$ HOP show -h
```

```
Usage:
  HOP show [command]

Available Commands:
  address     hop miner's network layer address
  counter     hop miner's network layer address

Flags:
  -h, --help   help for show

Use "HOP show [command] --help" for more information about a command.
```


#### show address

```console
$ HOP show address -h
```

```
Usage:
  HOP show address [flags]

Flags:
  -h, --help   help for address
```


#### show counter

```console
$ HOP show counter -h
```

```
Usage:
  HOP show counter [flags]

Flags:
  -h, --help          help for counter
  -u, --user string   User's main address to show
```

