* Encryption: the process of converting data from a readable format to an encoded format
* Public key infrastructure (PKI):  an encryption framework that secures the exchange of online information
* Cipher: an algorithm that encrypts information. Brute-force attacks crack ciphers by trying every possible key, like testing every combination on a lock.  Longer encryption keys offer better security because they drastically increase the number of possibilities an attacker must try. However, longer keys mean slower processing.  Balancing speed and security is crucial for online data communication.

## Types of encryption
There are two main types of encryption:

* Symmetric encryption is the use of a single secret key to exchange information. Because it uses one key for encryption and decryption, the sender and receiver must know the secret key to lock or unlock the cipher.
* Asymmetric encryption is the use of a public and private key pair for encryption and decryption of data. It uses two separate keys: a public key and a private key. The public key is used to encrypt data, and the private key decrypts it. The private key is only given to users with authorized access.

## Approved Algorithms

Many web applications use a combination of symmetric and asymmetric encryption to balance user experience with data security.  As an analyst, you should be aware of the most widely-used algorithms.

### Symmetric Algorithms

Symmetric algorithms use the same key for both encryption and decryption.

*   **Triple DES (3DES):** A block cipher that encrypts plaintext in "blocks." It's based on the Data Encryption Standard (DES), developed in the early 1970s. DES used 64-bit keys (56 bits for encryption). 3DES applies the DES algorithm three times with three different 56-bit keys, resulting in a 168-bit effective key length. Despite the longer keys, many organizations are moving away from 3DES due to limitations on the amount of data that can be encrypted. However, 3DES is likely to remain in use for backward compatibility.

*   **Advanced Encryption Standard (AES):** One of the most secure symmetric algorithms today. AES generates keys of 128, 192, or 256 bits. These key sizes are considered safe from brute-force attacks.  It's estimated that brute-forcing a 128-bit AES key could take a modern computer billions of years!

### Asymmetric Algorithms

Asymmetric algorithms use a pair of keys: a public key for encryption and a private key for decryption.

*   **Rivest Shamir Adleman (RSA):** Named after its creators at MIT, RSA was one of the first asymmetric encryption algorithms. It generates public and private key pairs. Asymmetric algorithms like RSA often use longer key lengths, partly because they generate two keys. RSA key sizes are 1024, 2048, or 4096 bits. RSA is mainly used to protect highly sensitive data.

*   **Digital Signature Algorithm (DSA):** A standard asymmetric algorithm introduced by NIST in the early 1990s. DSA generates 2048-bit key lengths. This algorithm is widely used today as a complement to RSA in public key infrastructure (PKI).

### Obscurity is not security

In the world of cryptography, a cipher must be proven to be unbreakable before claiming that it is secure. According to [Kerckhoff’s principle](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle) cryptography should be designed in such a way that all the details of an algorithm—except for the private key—should be knowable without sacrificing its security. For example, you can access all the details about how AES encryption works online and yet it is still unbreakable.

## Hashing
Hashing is widely used for authentication and non-repudiation, the concept that the authenticity of information can’t be denied. Hash functions are algorithms that produce a code that can't be decrypted. Hash functions convert information into a unique value that can then be used to determine its integrity. 

MD5, an early hash function, was created in the early 1990s to verify file transfers. It converts data into a 128-bit (32-character) value.  Any change to the original file creates a new hash.  However, its 128-bit length makes it vulnerable to hash collisions, where different inputs produce the same hash. This allows attackers to impersonate authentic data, as it's like copying someone's identity.  Because hash functions map infinite inputs to finite outputs, collisions are possible.

SHA (Secure Hash Algorithm) creates a unique, fixed-size "digital fingerprint" (hash) of any data.  It's a one-way function used for data integrity, password security, and digital signatures.  Different versions exist (SHA-1, SHA-2, SHA-3), with SHA-256 being widely used.  Key features include determinism (same input, same output), collision resistance (hard to find different inputs with the same hash), and the avalanche effect (small input change, big output change).

Rainbow tables
A rainbow table is a file of pre-generated hash values and their associated plaintext. They’re like dictionaries of weak passwords. Attackers capable of obtaining an organization’s password database can use a rainbow table to compare them against all possible values.

Adding some “salt”
Functions with larger digests are less vulnerable to collision and rainbow table attacks. But as you’re learning, no security control is perfect.
Salting is an additional safeguard that's used to strengthen hash functions. A salt is a random string of characters that's added to data before it's hashed. The additional characters produce a more unique hash value, making salted data resilient to rainbow table attacks.
