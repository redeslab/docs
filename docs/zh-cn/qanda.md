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

> 矿机已经加入到矿池，但是ContentNet中刷不到矿机

查看你的矿机是否和矿池在同一个内网，如果是请把矿池或者矿机安装在不同的网络环境。因为在同一个内网，矿机不能通过公网IP和矿池进行数据交流。


查看你的矿机是否打开了所有必要的端口，查看端口请使用netstat -nlp| grep HOP，如果您的矿机是假设在内网路由器后面，请进入您的路由器设置端口映射（port forward


查看你的矿机是否正确注册于BAS，查看方法为进入Pool的命令行或者在矿机下载BAS客户端，使用BAS命令查询（替换掉HO开始的矿机ID）：
./BAS query -b 103.192.253.122 -t 2 -a HO13cKPGckPUWcDc9cD2RkCJ1CwVc7NTTq4wQMb9isvRFX
如果能查询到矿机信息，你的矿池使用命令：./Pool show allminer 也能看到矿机，这说明你的矿机要么被防火墙挡住了，要么你的矿机的端口被限制了。


> 我的矿池已经注册了，但是没有在APP中找到矿池

请从https://docs.hopchain.org/#/zh-cn/ubuntu 下载ContentNet App, 该app是为中国地区特别订制的，所有Rinkeby测试网络的矿池和矿机都是架设于该网络之中。


在矿池中查询您的BAS注册信息（把ID替换成您的矿池ID，使用./Pool eth balance -d 命令查看矿池ID）：
./BAS query -b 103.192.253.122 -t 2 -a HO13cKPGckPUWcDc9cD2RkCJ1CwVc7NTTq4wQMb9isvRFX


如果不能查询到您的矿池，说明您的矿池要么没有注册成功，要么注册到了错误的网络中，请确认您的矿池配置文件~/.pool/conf.json和手册中的一致：
{
  "version": "1.1.7",
    "basip": "103.192.253.122",
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
        "apiUrl": "https://rinkeby.infura.io/v3/d64d364124684359ace20feae1f9ac20",
        "paymentService": "0xb7b93d75690C4d1E8110D8D86b09Ff43BcA4335a",
        "token": "0x72F391A5fC31b026739C8C26e0c5C01b2783F786"
      }
    }
}
