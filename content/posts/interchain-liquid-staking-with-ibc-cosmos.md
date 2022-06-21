---
title: "Interchain Liquid Staking With IBC Cosmos"
date: 2022-06-10T17:27:31+05:30
cover: "https://miro.medium.com/max/1400/1*86Ivs8UwWMoPfARfwYgSrQ.png"
---

Preliminaries 



>IBC is an interoperability protocol for communicating arbitrary data between arbitrary state machines.

IBC is an end-to-end, connection-oriented, state-
ful protocol for reliable, ordered, and authenticated communication between modules on
separate distributed ledgers



The protocol consists of two distinct layers: the transport layer (TAO) which provides the necessary infrastructure to establish secure connections and authenticate data packets between chains, and the application layer, which defines exactly how these data packets should be packaged and interpreted by the sending and receiving chains. IBC brings Cosmos closer to a truly interoperable ecosystem

IBC is a trustless bridge protocol that utilizes light clients, and cryptographic proofs to ensure
that the bridge has the same trust assumptions as the zones it bridges. This differs
significantly from oracle- or witness-based bridges, which rely on a small number of trusted
parties to verify that an event has taken place.

{{< tweet user="SanDiegoZoo" id="1389258127468531713" >}}



Those building applications that interact with IBC 
can use our Query & Transact secure read/write infrastructure 
to easily access blockchain data and build robust applications 
on 30 protocols, including IBC‐enabled Cosmos, Crypto.org Chain, 
and Terra.

<!-- what is IBC

working of IBC


Osmosis, Quicksilver, Injective Labs, Terra

terade DOT as cDot on cosmos

multichain interoperability
 -->

### Introduction

In proof-of-stake blockchain, asset holders wuishing to stake their tokens in order to earn staking rewards are required to lock their capital. This locked capital, knows as deligation, acts as slashable security deposit in the event that their chosen validators should misbehave.

Proof-of-Stake chosen over Proof-of-Work since they are faster, provides higher performance, Environmental sustaility and larger design space for economic incentives.


Staking with Cosmos (mostly includes proof-of-stake protocols) includes : 
* Delegator
* Validator

Validator runs hardware and a blockchain building using Cosmos SDK to propose blocks in consensus. Delegators put up capital in form of the chain's native staking token by way of security deposit

As a recompense for provoding security deposits, the delegators earn staking rewards proportional to value of their staked asets for each block validated. Validators in turn charge a commision upon these reqards for providing the validator service.

> Cosmos-SDK networks is five percent, leaving 95 percent of capital illiquid
and unutilized.



### Liquid Staking 

Liquids (crosschain assets) can be transferred, traded or utilised and this is implemented via set of smart contracts where the user deposits tokens in smart contract and some validators acting on behalf of the protocol are then delegated to by smart contract themselves.


>Derivative staked tokens are a claim to the underlying, illiquid staking positions that
remain exposed to above mentioned protocol limitations. These tokenized and thus liquid
representations of a claim can be used in various financial products. This means stakers
could earn additional yields or easily manage their risk exposure in various ways, e.g. with
respect to slashing risks associated with validators. We will expand on this type of
composability and highlight the potential benefits and risks of tokenized staking
positions in decentralized finance after introducing our taxonomy of liquid staking
approaches.
> — <cite>[Source](https://mirror.chorus.one/liquid-staking-report.pdf)</cite>

### How Interchain Liquid Staking Works

Since IBC was introduced, a new whole realm of oppurtunity was opened for developers to create a way to let users transfer, stake and transact assets of one chain throught a trustless bridge protocol using light clients and cryptographic proofs independent on oracles which only relies on small number of trusted providers.

Interchain Accounts: 

An application which enables IBC protocol having an Interchain Account ([ICS27](https://github.com/cosmos/ibc/blob/master/spec/app/ics-027-interchain-accounts/README.md)) which lets accounts on Network A be controlled by Netwirk B

Consisting on a Host and Contorller chain, the Controller chaon is able to register an account on Host chain by way of opening a dedicated IBC channel between the two chains.Interhcina assets staking protocols like quicksliver or interhcina asset AMM liek Osmosis increase the efficiency of delegating tokens on behalf users in turn minting  a tokenized representation of users's dekegations.


An interrchain staking for each chain will generate and control a deposit amount and number of delegation buckets by way of the interchain Accoubts IBC module

THis lets you deposit so as to recieve the transfer if tokenized delegation shares. Upon receipt of transfer into the deposit accounts, the corresponding address on the interchain staking chain will be credit with the appropriate asset of the value of the transferred delegation shares.

Given that validators are free to choose their own commission rates, a delegation to validator
A does not provide the same rewards over period T as an equal delegation to validator B. In
order to ensure fungibility between validators, we must be able to treat all delegations as
equal. In order to achieve this, we must socialize rewards such that all qAsset holders will
receive the same Asset rewards (that is, the collective Asset/qAsset redemption rate
will increase) as one other, regardless of the validators with whom they choose to delegate.

### Risk Socialization and Slashing

Similar to Reward Socialization above, given that validators are independent, run different
hardware and software configurations and are run by different teams with different experience
and priorities, the risk profile of each validator is different. In order to maintain fungibility,
this risk must also be socialized. A slashing event for one Asset validator is therefore borne
by all qAsset holders through a negative movement in the Asset:qAsset redemption rate.

Given sufficient decentralization across validators, slashing events are hedged against.
The outcome of such a double-sign slash (5%) for an average (1% of managed supply)
validator, will lead to a 0.05% reduction in the redemption rate; similarly, the same validator
being jailed for downtime (0.1%) will lead to a 0.001% reduction in the rate


----- 

In conclusion, it is clear that liquid staking is critical for the health of the staking paradigm, in
a world where better returns are available for an asset holder outside of delegation. Desigining an incentivised decentralisation protocol for interhcian liquid staking might ensure solid liquid staking solution on Cosmos.


