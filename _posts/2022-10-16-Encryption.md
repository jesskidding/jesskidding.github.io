---
title: "Encryption"
date: 2022-10-16
---
# Cybersecurity Resources

### Ciphertext:
- Encrypted information, known as ciphertext, is the product of deciphering plaintext.

### Cipher:
- The process of encrypting and decrypting information is called a cipher.
While most modern ciphers are cryptographic, many older ciphers, such as Caesar, are not.

### Encryption:
- To encrypt anything is to use a cipher to convert the information to unreadable ciphertext.

### Plaintext:

- Plaintext refers to information in its unencrypted form, which is often text but is not limited to that.
It might be a picture or any other kind of document.

### Encoding:

- It is important to note that encoding is NOT a kind of encryption, but rather a means of representing data, like base64.
Capable of being undone at once.

### Key:
- A piece of information called a "key" is required in order to successfully decode the ciphertext and recover the plaintext.

### Passphrase:
- A passphrase is a string of characters that may be used in place of or in addition to a password to secure a key.

### Asymmetric Encryption:
- In asymmetric encryption, the encrypting and decrypting keys are distinct.
 
### Symmetric Encryption:
- The two processes of encryption and decryption use the same key in symmetric encryption.

### Brute Force:
- Brute force attacks on cryptosystems test all possible combinations of passwords and keys.

### Cryptanalysis:
- The practice of attacking cryptography by discovering a flaw in its mathematical foundations is known as cryptanalysis. 

### Crypto Math:
- Mathematical concepts of a certain kind are used often in cryptography. In other words, the modulo operator. This operator is built into, or accessible through library for, almost all major programming languages. Utilize a programming language for dealing with massive amounts of data. Since Python's integers may be arbitrarily large, it's an excellent fit, and an interpreter is readily available.Mathematical concepts of a certain kind are used often in cryptography. In other words, the modulo operator. This operator is built into, or accessible through library for, almost all major programming languages. Utilize a programming language for dealing with massive amounts of data. Since Python's integers may be arbitrarily large, it's an excellent fit, and an interpreter is readily available.

### SSH Private Keys and How to Use Them:
- Secure Shell (SSH) Keys

- Keys used for Secure Shell (SSH) access should be treated as passwords. These are private keys, and you should guard them carefully. Insecurely stored private keys allow unauthorized users to access any accounts associated with them.

- The SSH decryption password is not used as part of your user name on the server. Your system will never send out your passphrases.

- The need of a secure passphrase and private key is highlighted by the fact that John the Ripper might potentially attack an encrypted SSH key to discover the password.

- To use an SSH key to log into a remote system, you must first generate the keys on your computer and send the public key to the remote host. There is never a copy of the secret key stored on the computer being attacked. No one cares if you use a temporary key to access a CTF box.
Put these keys to use?

- The.ssh directory is used as the default OpenSSH key storage. If you've turned on key authentication, the authorized keys file in this directory will have the public keys that may be used to access the server. Due to the increased security provided by key authentication over password authentication, several distributions enable it by default. Key authentication is used solely by root users.

- However, in order for a private SSH key to function, the proper permissions must first be set up. The private key should be kept secret and accessible only by its owner (600 or stricter). SSH -i keyNameGoesHere user@host is the standard Linux OpenSSH client's authentication method.

### Assymetric and Quantum
- We probably won't have sufficiently strong quantum computers until 2030 at the earliest, but when we do, cracking RSA or Elliptic Curve Cryptography will be a breeze. This is because the mathematical problems on which these algorithms depend can be effectively solved by quantum computers.

- Codes: AES/DES and Quantum


- While 256-bit AES is now unbreakable, 128-bit AES keys are expected to be cracked by quantum computers in the near future.
In the same way as Double DES, Triple DES may be broken by quantum computers. 

# Encryption-Crypto 101
