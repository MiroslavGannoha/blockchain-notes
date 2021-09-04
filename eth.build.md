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
