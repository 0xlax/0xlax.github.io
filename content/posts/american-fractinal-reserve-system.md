---
title: "Marka: American Fractional Reserve System on Solana"
date: 2022-05-23T02:19:43+05:30
description: "Implimentation of American Fractional Reserve System in Solana"
cover: https://media.bizj.us/view/img/1120091/bank-vault-thinkstock*750xx2807-1579-0-222.jpg
tags: [
    "AMM",
    "Dapps",
    "Solana",
]
---


##  Implimentation of American Fractional Reserve System in Solana




```Blog and Code in production :)```

### History

Modeled in 1660s, Fractional reserve banking lead to the invention of paper money.

A economic institution of the government initialised to manage the total supply of U.S Dollars 
which includes creation of fresh money too [not minting]. 

---

There are blockchain protocols building under FRB system but not preferred. Since, the fluctuations can cause adverseral damage to ones collateral unless its a *stablecoin*. But core reason of Marka is to understand the mathematical indications and reservational transactions.

{{< tweet user="SanDiegoZoo" id="1296074308301791236" >}}


### What is FRB

In the paper world, a central bank institutionalised by the government has the authority to print money. Pulled into circulation via bonds or securities.

Consider a commercial/private under which the sellers deposit the paper money. The bank follows *Fractional Feserve Lending* [FRL] where it keeps only fraction of the reserve and lends the rest to other business/people as loans, etc. 

If Alice deposits $10 into Bank A at a reserve rate of 10% the bank lends the rest of the money, that is $9 to Bob who inturn deposits it into Bank B which reserves a fraction (3%) and lends the remaining $8.73 of into Clara depositing it into Bank C.

The system now has escalated into a total amount of $27.73 from $10. This is knows as the *Money Multiplier Theory*

>The money multiplier measures the maximum amount of money that commercial banks can create by a given unit of central bank money. In other words, the total amount of loans that commercial banks are allowed to extend is a multiple of the reserves and this multiple is the inverse of the reserve ratio.
>                                ---  Injective Labs


One important requirement of this system in Cryptoworld is that there is no legal protection for crypto assets, pulling a backup from governance/Foundations/operators requires following a nested requirments which is not immediate and takes quite a while to bring into action. Where as with reserves, an automated balance is maintained.

And, in traditional banking system, Banks create the vast majority (about 90%) of the “money” that exists in an economy. Through bank charters, society grants the exclusive right to banks to create most of the money supply as well as with loans to borrowers funded by creating matching deposit accounts based on confidence. 

Core philosophy on FRB is its based on dihonest. Lettting users believe their money is safe in the bank while the bank invests it into other money creation schemes. In Defi, a user stakes it in a lending pool earning interest as a whole by mone being borrowed. Technically, its the same logic. 


Trading of stablecoins without permission and automatically by using liquidity pools instead of traditional market of buyers and sellers whilst maintaining a constant vlaue. An AMM based on FRB might work on other volatile assets with few mathematical complication which I am not equipped to work on at the moment. 

### Constant Product Formula

AMMs have become a primary way to trade assets in the DeFi ecosystem, and it all began with a blog post about “on-chain market makers” by Ethereum founder Vitalik Buterin. The secret ingredient of AMMs is a simple mathematical formula that can take many forms. The most common one was proposed by Vitalik as:

tokenA_balance(p) * tokenB_balance(p) = k

and popularized by Uniswap as:

x * y = k

### Money Maker

There are 2 different types of lending FRB AMM can propose. A Pool based lending or Vault based lending.
The only advantage of borrowing from vault is Flash Loans.

### 
* Create liquidity pools of similar assets such as stablecoins - offcer lowers rates of efficient trades
* Expand flexibility by creating pools across different assets
* Create pool with 50/50 ratio with a reserve system 
* Extract 3% from each asset deposit to be reserved in a secure vault for Flash Loans






##  [Marka](https://github.com/Marka-protocol/marka)

Introducing [*Marka*](https://github.com/Marka-protocol/marka),  a dAPP designed as a replication of Fractional Lending (and Borrowing) system including reserve ratios, treasuries [vault] and multiplier effect or yield aggregation. 












