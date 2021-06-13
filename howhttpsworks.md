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

### [They Handshake](https://howhttps.works/the-handshake/)
1. **Client Hello** - Browser sends a list of SSL/TLS versions and encryption algorithms that it can work with to a server.
2. **Server Hello** - Server chooses the best SSL/TLS version and encryption algorithm among the ones browser sent me, and based on my preferences. And replies with a certificate, which includes public key, so they can verify who the host is.
3. **Client Key Exchange** - Browser checks server's certificate to make sure they are legit. Then generates a 'pre-master key' so both sides can use it later when we generate a unique key. Browser encrypts that pre-master key with server's public key and then sends it to him.
4. **Change Cipher spec** - server decrypts the pre-master key using its private key. Then server and client generate the same 'shared secret' that they are going to use as a symmetric key.
5. **Everything is now secured** - Now all data going back and forth between client and server is now secured for the rest of the session.

### [HTTPS SSL TLS - differences](https://howhttps.works/https-ssl-tls-differences/)
* **HTTP** (HyperText Transfer Protocol) is the protocol used by your browser and web servers to communicate and exchange information.
* **HTTPS** is the secured version of HTTP.
* When that exchange of data is encrypted with **SSL/TLS**, then we call it HTTPS. The 'S' stands for Secure.
* **SSL** stands for 'Secure Sockets Layer'. A protocol created by Netscape.
* In 1999 Netscape gave control of SSL protocol to the **IETF**: Internet Engineering Task Force.
* Before 1999 ended, IETF released **TLS** version 1.0 (Which was really SSL 3.1).
* **SSL 3.0** was officially deprecated in 2015.
* Click [here to check](https://clienttest.ssllabs.com:8443/ssltest/viewMyClient.html) the current TLS version for your browser.
* **TLS 1.3** brings great security improvements and removes old weaker features. TLS 1.2 is still the recommended version if you are reading this in Spring/Summer 2020.

### [Certificate Authorities](https://howhttps.works/certificate-authorities/)
* A **certificate authority (CA)** is a third-party organization with 3 main objectives:
  1. **Issuing** certificates.
  2. **Confirming the identity** of the certificate owner.
  3. **Providing proof** that the certificate is **valid**.
* **Becoming a CA** is an intense task of security requirements and audits. You need to be trusted to be accepted into a root store.
* A **root store** is basically a database of trusted CAs.
* Apple, Windows, and Mozilla run their own root stores that they pre-install in your computer or device.
* When a CA issues a certificate, they sign the certificate with their root certificate pre-installed in the root store. Most of the time it's an intermediate certificate signed with a root certificate.
* How a certificate is validated. The process is based on a 'chain of trust'. Client looks up the entire certificate chain and if it is trusted, thus the site certificate is trusted as well.
