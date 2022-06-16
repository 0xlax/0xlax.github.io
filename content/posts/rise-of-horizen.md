---
title: "Rise of Horizen"
date: "2022-06-14"
description: "Exploration of Horizen blockchain and its core technology, Sidechains-SDK, Zendoo, path to Privacy"
tags: [
    "zk-SNARKs",
    "Blockchain",
    "Dapps",
    "Cosmos",
]
cover: "https://www.horizen.io/assets/img/icons/page_media/logo_no_tagline_dark.svg"
---

Ever since I watched the Consensus2022 presentation by [Rob Viglione](https://www.twitter.com/robviglione) about zkSNARKs, made me curious how Horizen plans its scalability. This blog is a short deep dive into Horizen Blockchain and relevent comparisions.

### Horizen ($ZEN)

>Horizen is a general-purpose blockchain system with novel Cross-Chain Transfer Protocol (CCTP) that enables an unbound and fully
>decentralized sidechain ecosystem

A peer-to-peer, permissionless and incentivised network that enables you to build a custom blockchain and applicaiton on the layer using Sidechain-SDK, a development kit devised to deploy a blockchain with fully customisable features and Dapps using Horizen's scalability and extenisbility. Multiple convocations of sidechains (parallel chains) transmit messages to each other and the mainchain via CCTP.

As of writing, Horizen has 45k active nodes running with an stake requirement of 42 $ZEN at an average price of $15.08 and estimated earning per node of about $4.17 ($50.75 a year)

Horizen has an intense focus on enabling zero-knowledge protocol to let application verify information without revealing the information itself. This helps companies building supply chains  on Horizen share product data with customers without revealing sensitive information, 
like identities of people involved in supply chain or locations of factories


## Internals and Architecture

#### [Equihash](https://github.com/tromp/equihash) 

Horizen protocols focus on maximum functionality rather than design by following Bitcoin's core alongside the [Equihash Proof-of-Work](https://eprint.iacr.org/2015/946.pdf) with [Delayed block penalty algorithm](https://www.horizen.io/assets/files/A-Penalty-System-for-Delayed-Block-Submission-by-Horizen.pdf)


Equihash Proof of Work mining algorithm is a class of hash function like [ETHash](https://eth.wiki/en/concepts/ethash/ethash) solving computational intensive and memory intensive problems to generate the proof but in an instant. Nice trade ;)

Equihash is also used by ZCash, Bitcoin Gold and known for being [ASIC-resistant](https://en.wikipedia.org/wiki/Application-specific_integrated_circuit)


> * Uses BLAKE2b to compute 50 MB hash dataset from the previous blocks in the blockchain (until the current block).
> * Solves the "Generalized Birthday Problem" over the generated hash dataset (pick 512 different strings from 2097152, such that the binary >XOR of them is zero). The best known solution (Wagner's algorithm) runs in exponential time, so it requires a lot of memory-intensive and >computing-intensive calculations.
> * Double SHA256 the solution to compute the final hash.
> * uses proof-of-stake consensus protocol since mining corporations consider [ASIC miners](https://en.bitcoin.it/wiki/Mining_hardware_comparison)


#### Cross-Chain Transfer Protocol (CCTP)
 
{{< image src="/img/cctp.png" alt="CCTP" position="center" >}}

The above self-explanatory image depicts how CCTP works i.e, providing safe and secure coin transfer invocations between mainchain and the sidechain. "Transfer" of coins in this scenario is a process of burning and recreating the coins under different chains (either mainchain to sidechain or vice versa) with same metadata attached regarding the end destinations. Just like a regular transactions as in bitcoin and Ethereum, the chains use UTXO but with specific sidechain outfut (for initial transactions). A sidechain is a multi-feature customisable chain that runs parallel to the mainchain.

Basically, a 2-way per protocol that performs 2 operations:
* Foward Transfer
* Backward Transfer

All this might sounds familiar if you have been a cryptodev for a while... COSMOS!

Cosmos used IBC (Inter BLockchain Communication protocol) and CosmosSDK while Horizon uses CCTP and SidechainSDK. Though the functionality between IBC and CCTP are similar with respect to multichain interoperability, there are vast differences between them. Explained later.


#### Sidechains

A Horizen sidechain architecture is built using 3 components. Based on the designed components can be hight coupled or decoupled so it works independent from any particular sidechain implementation.

* Mainchain consensus protocol (MCP)
* Cross-Chain Transfer Protocol (CCTP)
* Sidechain Consensus protocol (SCP)

Multipurposeness in a sidechain can be achieved by designing a system so that MCP and SCP are completely [decoupled](https://arxiv.org/abs/1812.05441).

Check out [SidechainSDK](https://github.com/HorizenOfficial/Sidechains-SDK) to know more about building on Horizen


Latus Sidechain is one among the many sidechain in existance thatuses [Ourobous POS](https://eprint.iacr.org/2016/889.pdf)


#### IBC vs CCTP




  Inter-BLockchain Communication (IBC)                              | Cross-Chain Transfer Protocol (CCTP) 
----------------------------------------                            |-----
   Communication between Zones as well as with Hub                  | Modified version of CCTP called Zendoo for communication between mainchain and sidechains 
  IBC supports transport, authentication and ordering of layers     | CCTPs responsible for only forward and backward transfers
   IBCBlockCommitTx  and IBCPacketTx transactions are used to defined and verify sender and reciever |  CCTP leverages zkSnark techniques to esstablish decentralised and verifiable cros-chain transfers. Also, enables communication(burning and creation) with different sidechain without knowing their internal structure 







### References
[cryptobook](https://cryptobook.nakov.com/cryptographic-hash-functions/proof-of-work-hash-functions)
[Horizon Whitepaper](https://www.horizen.io/assets/files/Horizen-White-Paper.pdf)
[IBC](https://ibcprotocol.org/implementations)