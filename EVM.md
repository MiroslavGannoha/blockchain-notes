## [What is Ethereum Virtual Machine (EVM)? Programmer explains](https://www.youtube.com/watch?v=GPoze5RmDVU)

- **Solidity** is compiled to byte code
- **EVM** is a virtual CPU that executes this byte code
- **EVM** is distributed state machine
- **GETH** is an implementation of Ethereum protocol which and EVM is part of it
- **OE** - Open Ethereum os another implementation of Ethereum protocol
- You can run GETH and EVM on your machine which will mean you are a part of Ethereum network
- **Ethereum network** is just a number of machines that run GETH and EVM (**Nodes**) 
- **Smart contract** compiles into the byte code and when it gets deployed all machines in Ethereum network get copy of it
- When somebody calls smart contract all machines pull up a copy of smart contract and run the byte code and they give you the result. And this result often in a state change
- **State** - current state of blockchain or snapshot (accounts, amount of token, smart contracts). All machines in the network keep track of the state.
- EVM keeps track of the current state of the blockchain. This state can be changed through transactions. **Transactions** can interact with smart contracts which can change the state
- Due to that we can have world neutral compute infrastructure or neutral global ownership infrastructure
- **AMM**  (Like uniswap) - peer to peer instant trades. Runs on top of EVM
