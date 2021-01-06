---
layout: post
title: Cryptography basics - Key Exchange
subtitle: A brief introduction to MAC & KDF in cryptography
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/Key_Exchange.png
share-img: /assets/img/path.jpg
tags: [cryptography, security, DHKE]
---

In this final article on cryptography, we would take a look at Key Exchange algorithms. We would also take a closer look 
at the implementation of DHKE algorithm.

### Key Exchange

Key exchange (also key establishment) is a method in cryptography by which cryptographic keys are
exchanged between two parties, allowing use of a cryptographic algorithm.
There are two main types of key exchange algorithms – key agreement and key transport.
In key agreement, both the parties contribute towards negotiation of the shared secret. Examples of
such schemes are Diffie Hellman Key Exchange (DHKE) and Elliptic Curve Diffie Hellman (ECDH).
In key transport, only one of the parties contributes towards the shared key and the other party obtains
it. They are generally implemented via public key cryptography.

#### DHKE Implementation

Here, we are going to have a look at the simplest and the original implementation of the protocol in
which we have two values p (a prime) and g (which is primitive root modulo p)
Let’s take a short detour and understand the primitive root modulo concept. I think that it is easier
understood with the help of an example. So, we have the numbers 3 and 7.
Here 3 is primitive root modulo 7.

This means that when all possible powers of 3 when divided by 7, will give us remainders 1,2,3,4,5 and
6. So, the remainders will be values from 1 to (7 – 1)

>3<sup>1</sup> = 3 -> 3 % 7 = 3
>
>3<sup>2</sup> = 9 -> 9 % 7 = 2
>
>3<sup>3</sup> = 27 -> 27 % 7 = 6
>
>3<sup>4</sup> = 81 -> 81 % 7 = 4
>
>3<sup>5</sup> = 243 -> 243 % 7 = 5
>
>3<sup>6</sup> = 729 -> 729 % 7 = 1

Thus, we say that 3 is primitive root modulo 7. 5 is also primitive root modulo 23.
Now we can understand how DHKE works. Two values, g and p, are hardcoded where g is primitive root
modulo p. In our case let g = 5, p = 23

We have two parties - Party 1 and Party 2. These parties will each come with up their secrets a and b.

We can take a = 2, b = 3
Now,

Party 1 will calculate the value A = g<sup>a</sup> % p

>A = 5<sup>2</sup> % 23 = 25 % 23 = 2 **(A = 2)**

Party 2 will calculate the value B = g<sup>b</sup> % p

>B = 5<sup>3</sup> % 23 = 125 % 23 = 10 **(B = 10)**

At this stage, both parties will share their values with each other.

Now,

Party 1 will calculate the value **B<sup>a</sup> % p (= g<sup>ba</sup> % p)**

>10<sup>2</sup> % 23 = 8

Party 2 will calculate the value **A<sup>b</sup> % p (=g<sup>ab</sup> % p)**

>2<sup>3</sup> % 23 = 8

We can see that both the parties arrive at the same value 8, and this will now be considered as the
shared secret.

One of the interesting features in DHKE is that even if somebody is able to intercept the communication
between the two parties, they will not be able to arrive at the common shared secret. This happens
because in computing, calculating exponents and modulo is an easy task. But the discrete logarithm
problem is not feasible. Thus for large values, the calculation becomes near impossible.
