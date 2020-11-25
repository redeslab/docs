## HOP Protocol Updates

### Pool and Miner version 1.0.0_gr has been released

2020-11-24 Update histroy:

1. Micro-payment systematically reconstruction. The ETH gas fee has been reduced to 1/3 and improve the stability of transaction and increse the speed of transction.

2. Add Pool bas command, the usage of bas is listed as below:

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

3. Add flag allminer, alluser, conf, income and etc... please check the complete list from below:

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

4. 