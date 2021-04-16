# Fintech_Hw_18


## Pre-Steps Required: 
- Install Mycrypto locally. 
- Install Geth.

## Part 1:

  - Start gitbash within the geth (in our case, Blockchain-Tools) folder.

  - Create First Node Account by running ./geth --datadir node1 account new Copy down information output by this command.

  - Create Second Node Account by running ./geth --datadir node2 account new Copy down information output by this command.

![Screenshot 1](https://github.com/MedakaRiceFish/Fintech_Hw_18/blob/main/Screenshots/Step%201.png)

---

## Part 2: 

- 1: Run ./puppeth.exe 
- 2: Choose network name 
- 3: Select option 2, "Configure New Genesis Block". A genesis block is the very first block in a blockchain. 
- 4: Select Option 1 "Create New Genesis From Scratch" 
- 5: Select Option 2 "Clique -- proof-of-authority". Proof of Authority is essentially a centralized method of producing the supply. 
- 6: Decide on block generation time (1 second in our case). A block generation time dictates the speed at which we want blocks to be mineable, and with bitcoin will adjust difficulty to ensure consistent block time. 
- 7: Fill out the sealer addresses (x2) with the addresses that were output from Step 1 (Node1 and Node2 Addresses) 
- 8: Pre-fund at least one of the addresses from Step 1 
- 9: Do not pre-compile addresses 
- 10: Allow for randomly generated chainID. A ChainID is a unique identifier to in the signature that identifies this specific chain. 

Congrats, new Genesis block created

![Screenshot2](https://github.com/MedakaRiceFish/Fintech_Hw_18/blob/main/Screenshots/Step%202.png)

---

## Part 3: 
- 1: initialize the nodes by using the following commands - 
  - Node 1: ./geth init rhhw18.json --datadir node1 
  - Node 2: ./geth init rhhw18.json --datadir node2
![Screenshot3](https://github.com/MedakaRiceFish/Fintech_Hw_18/blob/main/Screenshots/Step%203.png)

---

## Part 4: 

- 1: Start mining with each node with the following commands. Best to open each of these in a seperate command window. 
  - Node 1: ./geth --datadir node1 --unlock "0x3c1897427e87C17EE8274cFE1b51E0e86eeF48ae" --mine --rpc --allow-insecure-unlock
    - datadir is the direction in the command to navigate the directory
    - node1 is the name of the node
    - The address listed is the "sealer 1" address, and is the public address of node 1. 
    - mine starts the node into mining mode.
    - rpc is us telling the system which port to use
    - insecure unlock - allows you to unlock over http
  - Node 2: ./geth --datadir node2 --unlock "0x5e7139aE663F3A5824B7e3BF06032D3A38BC5863" --mine --port 30304 --bootnodes "enode://a7db6d2f0a784da4c892e5ef5fe05a3b6dcddfb7008c7e1e6e32927e42a9720b48a65cf087e11bb1959dcc5f159c9e3573b716f7b7bf8d9552ceacfff82d961a@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

![Screenshot4](https://github.com/MedakaRiceFish/Fintech_Hw_18/blob/main/Screenshots/Step%204.png)

---

## Part 5: 

- 1: Change your network in Mycrpto: (Create new custom node, grab your ChainID from Part two, and setup node) 
- 2: Verify you now see a premined balance in your new custom node for sealer 1 address. 
- 3: Send any amount to Sealer 2 address, and verify TX with the "Check Transaction" feature in mycrypto.

![Screenshot5](https://github.com/MedakaRiceFish/Fintech_Hw_18/blob/main/Screenshots/Step%205.png)
![Screenshot6](https://github.com/MedakaRiceFish/Fintech_Hw_18/blob/main/Screenshots/Step%206.png)
