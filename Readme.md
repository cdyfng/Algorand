mkdir ~/inst
cd ~/inst
mkdir ~/node
./update.sh -i -c stable -p ~/node -d ~/node/data -n

./goal node start -d data
pgrep  algod

goal node status  -d data/
Last committed block: 58510
Time since last block: 0.0s
Sync Time: 1931.5s
Last consensus protocol: https://github.com/algorandfoundation/specs/tree/5615adc36bad610c7f165fa2967f4ecfa75125f0
Next consensus protocol: https://github.com/algorandfoundation/specs/tree/5615adc36bad610c7f165fa2967f4ecfa75125f0
Round for next consensus protocol: 58511
Next consensus protocol supported: true
Genesis ID: testnet-v38.0
Genesis hash: 4HkOQEL2o2bVh2P1wSpky3s6cwcEg/AAd5qlery942g=


carpenter -d data
来可视化的查看日志。carpenter程序会一直运行，可以通过 Ctrl-C退出carpenter。

goal wallet new t_wallet_001 -d data
在创建账户之前，我们需要创建一个新的钱包：

goal account new -d data
Please enter the password for wallet 't_wallet_001': 
Created new account with address ROPDQKGD5DDWCUPXYAD6XRAJKVAIUUAJV7T4R2GTVF7CL6QD226VB4BUGM

goal account addpartkey -a  ROPDQKGD5DDWCUPXYAD6XRAJKVAIUUAJV7T4R2GTVF7CL6QD226VB4BUGM --roundFirstValid 100 --roundLastValid 3000 -d data
