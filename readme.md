Leaderboard available here. You should register in the leaderboard if you wanna be eligible for rewards.
Official documentation available here.
You can check the current network height in the explorer.
Ironfish is a miner software, so be aware of that when you choose your hosting provider (Webtropia for example). If you want continue use Webtropia – choose Dedicated servers.
One-line installation script is available:

wget -q -O ironfish.sh https://api.nodes.guru/ironfish.sh && chmod +x ironfish.sh && ./ironfish.sh && unalias ironfish 2>/dev/null
Choose you wanted option (for example option 1 – simply installing the node), enter preferred node name and wait for installation to complete.

Then execute the following commands:

The steps below are optional, you only need to start mining to increase your balance, and mining will start as soon as you sync the node. By default, a wallet is created with the default name, which used for mining rewards, so you do not need to create a new one.
1) Load variables:

. $HOME/.bashrc
. $HOME/.bash_profile
2) Set your node name (if you have empty config, you can check that by the command cat $HOME/.ironfish/config.json)

ironfish config:set nodeName $IRONFISH_NODENAME
ironfish config:set blockGraffiti $IRONFISH_NODENAME
The name you specify here should also be specified when registering in the leaderboard.
3) Create wallet:

ironfish accounts:create $IRONFISH_WALLET
4) Set created wallet as default wallet:

ironfish accounts:use $IRONFISH_WALLET
5) Check your balance:

ironfish accounts:balance $IRONFISH_WALLET
Additional
Before starting the miner, make sure that your node is synchronized with the network by running the command:
ironfish status -f
Enable Telemetry:
ironfish config:set enableTelemetry true
Send a transaction using your default account:
ironfish accounts:pay
If you want to send the transaction from another account, you can use the `-f` flag
.

ironfish accounts:pay -f MySecondAccount
In order to receive a transaction, you just need to tell the sender the public key of your account. If you do not know your public key, run the following command:
ironfish accounts:publickey
To get the public key of your another account running the command:
ironfish accounts:publickey -a MySecondAccount
View the list of accounts on your node:
ironfish accounts:list
Export an account to a file:
ironfish accounts:export AccountName filename
Import an account from a file:
ironfish accounts:import filename
Delete your account:
ironfish accounts:remove MyAccount
You can get information about connection status and errors by running the following command:
ironfish peers:list -fe
Export keys:
mkdir -p $HOME/.ironfish/keys
ironfish accounts:export $IRONFISH_WALLET $HOME/.ironfish/keys/$IRONFISH_WALLET.json
Import keys:
ironfish accounts:import PATH_TO_THE_KEY
Check ironfish status:
ironfish status -f
Check the node:
journalctl -u ironfishd -f
Check the miner:
journalctl -u ironfishd-miner -f
Stop the node:
service ironfishd stop
Stop the miner:
service ironfishd-miner stop
