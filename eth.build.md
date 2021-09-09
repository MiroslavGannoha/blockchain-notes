## ETH.BUILD Course notes
### [Hash Function](https://youtu.be/QJ010l-pBpE)
* It is basically like a fingerprint
* Output - 64 length hexadecimal string (it provides a human-friendly representation of binary-coded values)
* Same input - always the same output (deterministic)
* Hash string is one directional - only possible to guess secret with "brute force"
* Any little change in input string will change output hash function completely


### [Key Pair](https://youtu.be/9LtBDy67Tho)
* We generate **private key** from a secret using a hash function
* We derive **public key** from a private key using Elliptic-curve cryptography (ECC)
* We derive **address** from a public key
* Message + private key = **signature** (hash string)
* Signature + message = public address (or public key)
* We can sign data with our private key and then people can prove that it was us that signed it

### [Encryption](https://youtu.be/LGEBqz1uG1U)
* Anybody in the world knowing your public key can encrypt you a message send it publicly and only you with your private key can read that **public message**
* **Symmetric** cryptography - shared secret (key), each side has own copy of it, and can encrypt/decrypt messages
* **Asymmetric** cryptography - key pair, anyone can encrypt a message to your key pair
* **TLS** - asymmetric cryptography to set up a secret to have symetric cryptography
* **Address** = end of hashed public key
* You can take a public key and send a message to the public that will be opened only private key pair holder, but they won't know who the sender is. So you take a message, you sign it, you encrypt it with their public key, they get it back, they decrypt it with their private key, and then they recover the message, and get the sender address. So they not only can read it but also prove who the sender was.

### [Distributed Ledger](https://youtu.be/z11wj9OcA4U)
* A **distributed ledger** (also called a shared ledger or distributed ledger technology or DLT) is a consensus of replicated, shared, and synchronized digital data geographically spread across multiple sites, countries, or institutions. Unlike with a centralized database, there is no central administrator.
* A **peer-to-peer network** is required as well as consensus algorithms to ensure replication across nodes is undertaken.
* **Replay attack** when a fraud can publish a message many more times within the network when it is supposed to be sent only once
* **Nonce** ("number used once") one time integer that tracks your transactions to prevent publishing a message (transaction) multiple times

### [Byzantine Generals](https://youtu.be/c7yvOlwBPoQ)
* The Byzantine Generals Problem is a term etched from the computer science description of a situation where involved parties must agree on a single strategy in order to avoid complete failure, but where some of the involved parties are corrupt and disseminating false information or are otherwise unreliable.
* The agreement between all of these nodes (generals) is called **consensus**.
* Anyone can send messages into the network but only generals that have an army will be able to do enough **"proof-of-work"** to prove that their message authentic.

### [Blockchain](https://youtu.be/zcX7OJ-L8XQ)
* Nonce lets us tweak the hash of the block, thus we are doing work finding a leading zero of a hash
* The previous block's hash is going to be part of the next block this is how the **chain of blocks** is formed
* Trying to find nonce we are basically mining, we are using our limited CPU power to arbitrarily throw random hashes at this until we find the hash that has the required amount of leading zeros
* **Coinbase** - link to a miner in the block
* To incentivize the miners who are spending money to buy the rigs and secure the network, with all their hash power, we give them a cut called the **block reward** of each block that they mined.
* In a situation where two new blocks mined concurrently by two different miners, the miner with the **longest valid chain** wins, but the reward gets split between both of them
* As the blocks are mined they become more and more secure. Because if at least one tiny little piece in one of the blocks gets changed all blocks become invalid, because their hashes will lose leading zeros. So you can't change anything once the block is already mined.


### [Transactions](https://youtu.be/er-0ihqFQB0)
* Thousands of people in the pool are bidding, fee is like a bid, miners pick transactions from the pool, and put them into the block.
* Transaction consist of - value, data, gas, gasPrice, nonce, to(address). "From address" is derived, because the sender signs the transaction with his private key before sending it.
* Decimals are not supported by the system so because of that everything is converted to wei under the hood.
* 10^18 wei = 1 eth, 10^9 wei = 1 gwei(giga wei).

### [Meta Transactions](https://youtu.be/CbbcISQvy1E)
* To deploy a smart contract we send a transaction without a "to" address, and the "data" of a transaction is the byte code of a contract.
* To talk to a contract we can send another transaction to the smart contract address and in the "data" field we will have a call data.
