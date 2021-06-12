## [How HTTPS works notes](https://howhttps.works/)

### [Why do we need HTTPS](https://howhttps.works/why-do-we-need-https/)
* **Privacy** - using http someone can eavesdrop on your messages, as they are not encrypted
* **Integrity** - "man-in-the-middle attack" threat
* **Identification** - A digital signature attached to a message can identify the sender.
* HTTPS, via SSL certificates, ensures you are connected exactly with the receiver you would expect.

### [They Keys](https://howhttps.works/the-keys/)
* **Symmetric key algorithm** - only one key to encrypt and decrypt a message, only the person that has a copy of the key can decrypt and read the message
* One **main issue with symmetric keys** is that they are hard to share.
* **Asymmetric keys** - The main difference with symmetric keys, is that you have **2 keys**. One key is **public**, the other one is **private**. They are paired and work together. 
* Only the **private key** can open a box locked with the **public key pair**.
* Great not only for **privacy**, but also for **identification** since we know for sure that only the owner of the 2 keys can open the message.

