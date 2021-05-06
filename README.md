# Blockchain_HW

# Summary
* Set up a custom private testnet blockchain
* Send a test transaction

# Disclaimer
See screenshots titled 'Launch Node 1' and 'Launch Node 2'. 

When launching the nodes, I kept getting the message "looking for peers" followed by this error message: ERROR[05-05|20:27:04.672] Snapshot extension registration failed   peer=89027a8b err="peer connected on snap without compatible eth support

A google search leads me to think this could possibly be a storage problem and I keep getting low storage errors on my computer. I'm still trying to troubleshoot this. 

I've tried to delete geth from the node with the following code: m -Rf node1/geth node2/geth
followed by a node restart multiple times, but I simply cannot get it to work. 

# Downloads
* Go Ethereum is an ethereum protocol and we used it to create our blockchain. It can be downloaded here: https://geth.ethereum.org/downloads/

* MyCrypto is a free open source interface that allows us to interact directly with the blockchain. We used this app to manage our ethereum wallets and transact in the blockchain. It can be downloaded here:  https://download.mycrypto.com/


# Configurations of Network
After running puppeth in Go Ethereum, we configured a genesis block using the Proof of Authority consensus algorithm. The PoA consensus algorithm leverages the value of identities, which means that block validators are not staking coins but their own reputation instead. Therefore, PoA blockchains are secured by the validating nodes that are arbitrarily selected as trustworthy entities.

Blocktime:
Chain ID: 999
Password: Fluffy10!
Network Name: Homeworknetwork

# Code 
## Initialize Nodes: 

./geth --datadir node1hw init homeworknetwork.json

./geth --datadir node2hw init homeworknetwork.json

## Launch Nodes:

./geth --datadir node1hw --unlock "0xc94436665eFAB753B643Fd90fF1C24B3A3CBbEb1" --mine --rpc --allow-insecure-unlock

./geth --datadir node2hw --unlock "0x89b1E3126132DA8a3fE93FCFee20BD86aA3BDf0B" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

# Connect MyCrypto

* Create a custom node to connect to the custom network that was set in the genesis block
* Send money between accounts 