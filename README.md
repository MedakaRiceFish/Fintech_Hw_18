# Fintech_Hw_18


## Pre-Steps Required: Install Mycrypto locally. Install Geth

-Part One: (see step 1 screenshot)

Create First Node Account by running ./geth --datadir node1 account new Copy down information output by this command.

Create Second Node Account by running ./geth --datadir node2 account new Copy down information output by this command.

---

## Part Two: (see step 2 screenshot)

1: Run ./puppeth.exe 2: Choose network name 3: Select option 2, "Configure New Genesis Block" 4: Select Option 1 "Create New Genesis From Scratch" 5: Select Option 2 "Clique -- proof-of-authority" 6: Decide on block generation time (1 second in our case) 7: Fill out the sealer addresses (x2) with the addresses that were output from Step 1 (Node1 and Node2 Addresses) 8: Pre-fund at least one of the addresses from Step 1 9: Do not pre-compile addresses 10: Allow for randomly generated chainID Congrats, new Genesis block created

---

## Part 3: (See step 3 screenshot)

1: initialize the nodes by using the following commands - Node 1: ./geth init rhhw18.json --datadir node1 Node 2: ./geth init rhhw18.json --datadir node2

---
## Part 4: (See step 4 screenshot)

1: Start mining with each node with the following commands. Best to open each of these in a seperate command window. Node 1: ./geth --datadir node1 --unlock "0x3c1897427e87C17EE8274cFE1b51E0e86eeF48ae" --mine --rpc --allow-insecure-unlock Node 2: ./geth --datadir node2 --unlock "0x5e7139aE663F3A5824B7e3BF06032D3A38BC5863" --mine --port 30304 --bootnodes "enode://a7db6d2f0a784da4c892e5ef5fe05a3b6dcddfb7008c7e1e6e32927e42a9720b48a65cf087e11bb1959dcc5f159c9e3573b716f7b7bf8d9552ceacfff82d961a@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

---

## Part 5: (See step 5/6 screenshot)

1: Change your network in Mycrpto: (Create new custom node, grab your ChainID from Part two, and setup node) 2: Verify you now see a premined balance in your new custom node for sealer 1 address. 3: Send any amount to Sealer 2 address, and verify TX with the "Check Transaction" feature in mycrypto.
