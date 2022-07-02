---
title: "Eth2, The Merge and L1s"
date: 2022-06-01T16:59:52+05:30
cover: "https://ethereum.org/static/5d3af9eb308978e7a078bf51022d8a5c/24462/merge.webp"
Description: ETH2, The Merge and comparision with other L1s
tags: [
    "ETH2",
    "Beacon Chain",
    "L1",
]
---

### Introduction

Prices of L1s are known to be volatile and its hard to spin a number on its valuation. Instead, using metrics as Total Value Locked, number of transactions and users count we will see the comparision of Eth2 with other L1s. With Ethereum’s upcoming transition from Proof of Work (POW) to Proof of Stake (POS), we can now use staking yields as a basis of comparison across all Layer-1 tokens.


### The Merge 🐼

![Panda for context](https://pbs.twimg.com/media/FSkMcTDVEAEFsAR?format=png&name=small)



The Beacon Chain, a Ethereum POS network has been running parallel with Ethereum since December 2020. The transition from POW consensus to POS has been awaited and anticipated by many. On the merge, the Ethereum's POW consensus layer will be removed and all future blocks on Ethereum are expected and will be achieved by the then merged Beacon Chain's POS Consensus layer. 








The Ethereum team has been workign on making this happen along with series of other tests and conducts that regulate the process and safety after the merge including the [Kiln public testnet Merge](https://blog.ethereum.org/2022/03/14/kiln-merge-testnet) in March and the most recent [4th shadow fork](https://twitter.com/sassal0x/status/1524756386063667200?s=20&t=QZIo6qDUhC8ySoYwtfDbvA) 

{{< tweet user="SanDiegoZoo" id="1506779959242764288" >}}

> Merge is expected to happen in Q3/Q4 2022.


The important takeaway from the Merge is that it does not help scale Ethereum! If so what is the point then?

- Proof-of-Work concensus has a laborious requirement of energy. Miners running nodes in a POW system use powerful GPUs that requires vast amount of electricity to run the calculations and cryptographic puzzles - hashing algorithms that so as to keep the network and funds secure. Comparatively, any recent consumer hardware is capable of being ETH2 validator. And pushing a node to the network to participare in network's consensus algorithm with a minimum stake requirements of 32 ETH and if incase any sort of malicious activities by the validatos leads to [slashing](https://consensys.net/knowledge-base/ethereum-2/glossary/#slashing) of their staked funds.

In addition, since POW requires expensive hardware and electricity costs, ETH token inflation has been around 4.3% per year to compensate the miners for their work. With POS being more energy-efficient, the cost to secure the Ethereum network (token inflation) is much less. Ethereum’s POS issuance model is based on how much ETH is being staked. Currently, there are about 12.5M ETH staked on the Beacon Chain – at that level, annual issuance would be about 0.5%.

Although, this new merge is giving out opportunities to develop many  Proof-of-Stake distruibuted validator layer protocols and middleware clients. that enables you to run validators across other independent nodes safely. Like, [Charon](https://github.com/ObolNetwork/charon) from [Obol Labs](https://obol.tech) 

>Charon integrates into the Ethereum consensus stack as a middleware between the validator client and the beacon node via the official Eth Beacon Node REST API. Charon supports any upstream beacon node that serves the Beacon API. Charon supports any downstream standalone validator client that consumes the Beacon API.

One of the advantage of Chaon is you that you can participate in the network's consensus by staking only half the required stake amounts and eark equivalent rewards on your validator nodes. 



### ETH Staking

An yield return depends on the ETH staked which drives the staking returns 


* #### Yields based on ETH staked

| ETH Staked   | Max Annual Issuarance (ETH)    | Max Annual Issurance in %    | Staking Yield %  | Annual Burn (ETH)| Real Staking Yield % 
| --------  | -------- | ------ | --------  | -------- | ------ | 
| 1,000,000 | **181,019** | `0.15%` | `18.10%` | **-3,012,400** | `69.68%` 
| 3,000,000 | **313,534** | `0.26%` | `10.45%` | **-3,012,400** | `29.10%` 
| 10,000,000 | **572,433** | `0.47%` | `5.72%` | **-3,012,400** | `12.66%` 
| 12,500,000 | **624,814** | `0.52%` | `5.00%` | **-3,012,400** | `10.92%` 
| 30,000,000 | **991,483** | `0.82%` | `3.30%` | **-3,012,400** | `6.62%` 
| 42,000,000 | **1,131,833** | `0.94%` | `2.69%` | **-3,012,400** | `5.43%` 
| 66,000,000 | **1,412,534** | `1.17%` | `2.14%` | **bo-3,012,400** | `4.21%` 
#####  [source](https://docs.ethhub.io/ethereum-roadmap/ethereum-2.0/eth-2.0-economics/)

The above table estimations are upped with few assumptions excluding MEV, with the current ETH staked on Beacon chain(~10% supply, 12.5M ETH). 






* #### ETH Staking Yields vs Competing L1s

Looking at nominal yields, ETH is about middle of the pack compared to its major competitors, with yields ranging from 6.64% to 17.53% in nominal terms. However, with the exception of BNB, all of the other tokens in the competitive set are inflationary. Factoring in token issuance rates, ETH has the highest staking returns on a real yield basis.



![l1](https://lh4.googleusercontent.com/o0QJVZxOnt2JbuviicoFDC9570ZMkG-96ENyia3HAYT8wdLAPoblP1CtSqD0n1smRHo7SxhPdE8YSM9Ji6CpG-agF2mXWNkepqUroxJ7L4FFZkyxQQ9AkLPlCuQFJD7TddFPrnyd0J_-myYf-Q)


One point to note is that currently only 10.3% of ETH is staked on the Beacon Chain, which is the lowest in the competitive set and likely due to concerns about locking up ETH for a long time (withdrawals are not possible currently). Staking should increase post-Merge as the execution risk of the Merge is removed, ETH moves closer to enabling staking withdrawal, and more people grow comfortable with staking ETH. Staking participation amongst competing L1s ranges from 35% to 76% with an average of 55%. If ETH staking participation increases to the average of 55%, real staking yields for ETH would likely decrease to approximately 4.21%. At 55% of supply staked, ETH’s real yield would project to be higher than SOL, AVAX and MATIC, but lower than BNB, DOT, NEAR and FTM

After factoring in projected increases to circulating supply over the next year for the competitive set, ETH’s real staking yield net of dilution is the highest if we assume staking participation remains the same. If ETH’s staking participation reaches 55%, then ETH would rank higher than SOL, AVAX, NEAR and MATIC but lower than BNB, DOT and FTM.