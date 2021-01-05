---
layout: post
title: Cryptography basics - Hash functions
subtitle: A brief introduction to hash functions in cryptography
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/hash.jpg
share-img: /assets/img/path.jpg
tags: [cryptography, security, hashing]
---
What is cryptography and what is the first thing that comes to our mind when we hear the term. Well, I
asked this question to my friend and he answered that it has something to do with security. But he did
confess that he did not have a very clear idea about how it is done in our day to day lives. So, in this
article we will be going over some of the basic concepts involved in this domain. The first article in the 
series would be focussed on hash functions. We will visit other key concepts in later articles.

First, let’s start with the definition – Cryptography is the science of providing security and protection of
data. It involves storing and transmission of data in a way that the data is only accessible to those who
were intended to access it.
Cryptography involves two basic concepts – confusion and diffusion.
Confusion refers to the fact that every bit in the output cipher must depend on several parts of the input
string and key provided. And as such, there is no direct correlation available between the input and
output strings.
Diffusion means that a change of a single bit in the input stream should change approximately half of
the output bits.
Going forward, we would be examining the following concepts related to cryptography:
01. Hash functions
02. MAC (Message Authentication Code)
03. KDF (Key Derivation Function)
04. Key Exchange

### Hash functions
In computer programming, the primary function of a hash function is to map text to integers. In our case
of cryptographic hash functions, they are used to transform text/binary data to fixed length hash values
which have to be collision resistant and the process must be irreversible in nature.
In order to understand them better, let us take the example of an extremely basic hash function. Our
hash function will just add the individual letters in the input stream. However, such a function will have
many problems.
For example, we will consider a=1, b=2, c=3 and so on, and we will denote hash of input as H(input)
So, let us consider the two inputs – “abc” and “cab”
Thus,

>H(abc) = 1 + 2 + 3 = 6
>
>H(cab) = 3 + 1 + 2 = 6

So, we can clearly see that our basic hash function is not collision resistant and therefore not suitable for
cryptographic uses. The ideal cryptographic hash function must have the following properties:
1. Deterministic
The same input must always provide us with the same output
2. Quick
Our hash function should be able to compute the hash value reasonably quickly
3. Hard to analyse
Also referred to as diffusion, a small change in input must change the output value completely
4. Irreversible
Generating the input value from the output hash must not be feasible
5. Collision resistant
Good hash functions must be designed in a way that it is practically impossible to find two input values
which have the same hash value.
Some of the most important applications of hash functions are checking for document integrity and for
storing passwords. Instead of storing a plaintext password in a database, developers store hashes of the
password in the database for security reasons.

#### Secure Hash Algorithms

##### SHA-2, SHA-256, SHA-384, SHA-512
One of the most widely used hash functions, they are based on the Merkle–Damgård construction. They
are considered good enough for most commercial applications. Within this family, higher number of
output hash bits result in greater collision resistance.

So, SHA-512 > SHA-384 > SHA-256 where 512, 384 and 256 are the number of bits in the hash.

##### SHA-3, SHA3-256, SHA3-512, Keccak-256
These hash functions are considered to be more secure than SHA-2 functions for the same hash length.
These functions are based on the cryptographic concept of sponge construction and they are not
vulnerable to length-extension attacks.

Keccak-256 is a variant of SHA3-256 with some constants changed in the code.

SHAKE128(message, length) and SHAKE256(message, length) are variants of SHA3-256 and SHA3-512
where the output hash can be of any desired length.

*Some other hash functions are MD5, SHA-0, SHA-1 : but these should not be used as they are
considered to be cryptographically insecure.*
