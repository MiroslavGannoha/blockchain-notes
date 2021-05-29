## ETH.BUILD Course notes
### [Hash Function](https://youtu.be/QJ010l-pBpE)
* It is basically like a fingerprint
* Output - 64 length hexadecimal string (ti provides a human-friendly representation of binary-coded values)
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
