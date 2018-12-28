# blockchainJS
BlockchainJS is written in plain Javascript using ExpressJs and AngularJs. The blockchain in this case is very similar to a bitcoin blockchain in which the ledger contains transaction details like sender, recipient, amount, etc. It also has a user friendly block explorer to search the blockchain. It is a real time blockchain network where multiple nodes participate and mine and a single valid copy of the ledger is synchronised throughout the network.

# Functionalities
1. __APIs__<br />
  1.1 Create and broadcast transaction<br />
  1.2 Mine a block<br />
  1.3 Consensus (longest chain valid rule)<br />
  1.4 View entire blockchain<br /><br />
  
2. __Block Explorer UI__<br />
  2.1 Search by Block hash<br />
  2.2 Search by transaction Id<br />
  2.3 Search by address and view balance<br />
  
# Installation Steps
1. Clone the repo ```git clone https://github.com/jainanuj7/blockchainJS.git```
2. Browse into _blockchainJS_ directory
3. Install node packages ```npm install```

# Usage Steps
__1. Spawn a new netowrk node__ ```npm run node_1```<br />
Spawn second node ```npm run node_2```<br />
NOTE: You can create upto 5 nodes using default config. You can edit the config in _package.json_

__2. Synchronise the network__<br />
For eg to sync the node 1 and node 3,<br />
Send a POST request at ```http://localhost:3001/register-and-broadcast-node```<br />
Body:
```{
	"newNodeUrl": "http://localhost:3003"
}
```
Similarly you can sync as many nodes as you want.

__3. Create a new transaction__ <br />
Send a POST request at ```http://localhost:3001/transaction/broadcast```<br />
Request body eg:<br />
```{
	"amount": 5,
	"sender": "LLWWWZQQZZFSDFSDSDGFEFWEFR",
	"recipient": "KKVBNXXLLLNWERTYJFVDCSDWFETH"
} 
```
...some random transaction details <br />

__4. Mine the transaction__<br />
Send a GET request at ```http://localhost:3001/mine```

__5. Play around__<br />
Repeat the above steps to create as many transactions as you want

__6. Browse the Blockchain explorer UI__ at ```http://localhost:3001/block-explorer``` 


# Screenshots
![alt text](https://github.com/jainanuj7/blockchainJS/blob/master/screenshots/hash.jpg) <br /><br />

![alt text](https://github.com/jainanuj7/blockchainJS/blob/master/screenshots/transactionId.JPG) <br /><br />

![alt text](https://github.com/jainanuj7/blockchainJS/blob/master/screenshots/address.jpg) <br /><br />
