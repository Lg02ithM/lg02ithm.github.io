---
layout: post
title: Cryptography basics - MAC & KDF
subtitle: A brief introduction to MAC & KDF in cryptography
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/MAC.png
share-img: /assets/img/path.jpg
tags: [cryptography, security, MAC, KDF]
---
In this article, we would be going further into basic cryptography concepts and would take a look at Message Authentication Code or MAC
and Key Derivation Function (KDF). Also, this article is in continuation to the previous article on cryptography basics and hash functions.

### Message Authentication Code (MAC)

MAC refers to a cryptographic code calculated using a given key and a given input message. It behaves
as hash function and follows confusion and diffusion tactics as discussed above. Popular algorithms
include **HMAC** (Hash based MAC), **KMAK** (Keccak based MAC).
The main use case for MAC is authenticated encryption. Let’s understand the steps involved in the
process

01. A key is derived from the supplied password.
02. The message is encrypted using the above obtained key and the output cipher is stored.
03. We calculate the MAC code using the derived key and the original message. The same value is then
appended to the output cipher obtained in the previous step.

During decryption, the following steps are followed

01. We derive the key from the password entered by the user.
02. We decrypt the message using the obtained key.
03. We calculate the MAC code for the message and the key. We then check if the value matches the
one we obtained previously.

### Key Derivation Function (KDF)

These family of functions are used to transform a variable length password to a key of fixed length. Now, 
one might ask why not simply hash the password and be done with it. Well, this approach might lead to
dictionary attacks. A dictionary attack is defined as an attempt to get unwanted access by using a large
set of words to generate potential passwords.

Thus, in order to avoid these flaws, KDF’s use a salt as well as multiple iterations of computations make
the process more secure. In cryptography, a salt is random data that is used as an additional input in
order to prevent dictionary attacks. We also use the multiple iterations in order to speed down the
guessing process. As such, the KDF is a computationally expensive process.
Some examples of KDF are **PBKDF2**, **Bcrypt**, **Scrypt**, **Argon2**.

However, PBKDF2 has a weakness. It is not resistant to GPU/ASIC attacks. This happens because of the
fact that the process uses a relatively small amount of RAM.
Thus, we have better algorithms like SCRYPT and Argon which are resistant to these attacks. These
algorithms are similar to PBKDF2, but they are also memory intensive. Thus, memory access becomes
the main bottleneck for the calculations.

Some other techniques that can be used to deter attackers from brute forcing are the usage of captcha
and increased login delay with each incorrect attempt. 

Fun fact, captcha is an acronym for “Completely Automated Public Turing test to tell Computers and Humans Apart”.
