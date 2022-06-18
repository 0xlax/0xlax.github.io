---
title: "X25519 Elliptic Curve "
date: 2022-06-02T20:20:36+05:30
cover: "https://hsto.org/webt/qy/r5/a6/qyr5a6ywaf8vbc2kxtaazdmvgz8.png"
description: "A state-of-the-art Diffie-Hellman protocol"
tags: [
    "cryptography",
    "ECDH",
]
categories: [
    "Elliptic Curves"
]

---


<!-- Overview of algorithimc rust implementation of x25519 WIP -->

x25519 is a fast, secure [Curve25119 ECDH](#terminology) function which lays the foundation of almost all field of software including Operating sytems, Network, TLS Libraries and Blockchains.



>An attacker who spends a billion dollars on special-purpose chips to attack Curve25519, using the best attacks available today, has about 1 chance in 1000000000000000000000000000 of breaking Curve25519 after a year of computation
> — <cite>[Dan Bernstien](https://dnscurve.org/crypto.html)</cite>

### X25519




To understand x255219, it is crucial to understand the underlying basics Elliptic Curve Cryptography, ECDH key exchange protocol, Curve25119 and coordinate based equations.






Bernstein contructed the Diffie-Hellman Key exchange protocol *X25519*  based on Curve25519. As known from the Eliptic curve cryptography demonstrating how the coordinates are mapped to obtain a key, X25519 follows the same paradim but only depends on x coordinate of the point on the elliptic curve. This was source in through Victor Millier's [Use of Elliptic Curves in Cryptography"]("https://link.springer.com/chapter/10.1007/3-540-39799-X_31")

Calculating a point based on x-coordinate and the curve equations is done is various ways- using the algebraic structure of the point group (the presence of the 4th order point) on the Montgomery curve is less computationally intensive with the Montgomery Ladder Algorithm and is easier to implement in constant time. This is why Bernstein chose the Montgomery curve.

In the practical application of ECDH, top priority should be given to the check of messages received. In the typical ECDH protocol, both parties participating in the protocol will receive the temporary public key sent by the other party. To ensure security (to ensure their private key information will not leak), it is usually necessary to first check the legality of the received point. 

If the received point is the point deliberately constructed by the other party, the other party may steal the private key information through the interaction process of the ECDH protocol. If the check of the point is ignored, it may cause small subgroup attacks or invalid-curve attacks, etc. 

Similar problems exist in ECDH key exchange protocols that rely only on x coordinates. The difference is that it is more difficult to check the validity of the public key at this time, which is to determine whether the amount of received public key x calculated by the curve equation is the quadratic residual on the prime field. Since the square operation on the domain is a 2-to-1 mapping, only half of the x values are legal. In order to solve this problem, the design of the X25519 protocol innovatively takes into consideration the elliptic curve point group on the quadratic expansion domain, while considering the two elliptic curve point groups on the base domain and the quadratic expansion domain. Then the arbitrary value in the number field on the bottom layer can be used as a legal public key -- In the perspective of modulo operation, furthermore, any 32-byte array can be used as a legal public key value, thereby eliminating the need to check the validity of the public key. It is noteworthy that although the second expansion is introduced, all operations are still performed on the prime field of the underlying layer, that is, the introduction of the quadratic extension does not increase the computational complexity. Since the discrete logarithm remains difficult in the two curve point groups, the X25519 key exchange protocol is also safe.
















### Applications

* Protocols:
1. [QUIC](https://en.wikipedia.org/wiki/QUIC)
2. [TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security)
3. [SSH](https://en.wikipedia.org/wiki/Secure_Shell)










### Terminology


* ***Curve25519*** : Curve25519 is a Montgomery curve built by Bernstein in 2006, in which 25519 indicates that the characteristic of the bottom prime number field on which the elliptic curve depends is 2²⁵⁵-19

* ***Ed25519*** Ed25519 is the EdDSA signature scheme using SHA-512

* ***Diffie-Hellmman Key Exchange*** is a commonly used exchainge protocol which lets 2 different parties having a key pair exchain information through a insecure channel in a secure way without being eavesdropped by a third party. Once of my favourite source for understanding ECDH key exchange better is to watch this detailed explanation by [Computerphile](https://www.youtube.com/user/Computerphile)


{{< youtube id="NmM9HA2MQGI">}}




* ***Curve25519*** Curve25519 is a Montgomery Cruve built by Dan Bernstien in 2006, in which 25519 indicated that characteristic of the bottom prome number field on which the elliptic curve depends in **2<sup>255</sup> - 19**



#### References

[intro-ed25519](https://github.com/longcpp/CryptoInAction/blob/master/intro-ed25519/190902-intro-x25519.pdf) 
[ECDH protocol](https://en.wikipedia.org/wiki/Elliptic-curve_Diffie%E2%80%93Hellman)






<!-- https://coinexsmartchain.medium.com/a-deep-dive-into-x25519-7a926e8a91c7
https://medium.com/asecuritysite-when-bob-met-alice/youve-heard-of-x25519-but-what-s-so-special-about-x448-c790ef57ceb1
https://www.trustonic.com/technical-articles/field-arithmetic-for-curve25519/ 
https://medium.com/asecuritysite-when-bob-met-alice/the-fido2-and-post-quantum-cryptography-revolution-and-he-zkp-and-mpc-ccfc77ed5d85 
https://ianix.com/pub/curve25519-deployment.html-->



