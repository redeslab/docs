### 注册矿池 <!-- {docsify-ignore} -->

+ 矿池的注册命令和选项

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

+注册矿池

```console
$ Pool eth reg -e "youremail@address.com" -n "Pool_Name" -u "https://yoursite.com"
```

Ropsten测试网络

```console
$ Pool eth reg -d -e "youremail@address.com" -n "Pool_Name" -u "https://yoursite.com"
```

+ 使用您在初始化阶段设置的密码，这里使用123做为密码： 

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

>注册矿池的时间依照以太坊的转账时间为准, 请使用海盗dapp或者MacOS的客户端查看"流量市场"以确认您的矿池出现在那里面.

