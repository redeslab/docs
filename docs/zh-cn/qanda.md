> 如何重新初始化矿池和矿机

对于矿池请先把HOP和ETH备份或者转移到其他钱包地址，接下去矿池请删除.pool隐藏文件夹，矿机请删除.hop隐藏文件夹

具体命令如下：

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

> 如何重新初始化矿池和矿机