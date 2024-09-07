# Overview

In this article, I make a compelling case that explains why **blockchain without proof-of-work is nothing** *(well, technically not nothing, but simply a database)*.

My inspiration to write this comes from a research papaer I found from 1992 titled *Pricing via Processing or Combatting Junk Mail* by Cynthia Dwork and Moni Naor.

## Argument

In the realm of DLT *(distributed ledger technologies)*, blockchain has emerged as a "revolutionary" concept. The popular understanding of blockchain is that it promises transparency, decentralization and immutability. However, without a robust consensus mechanism like proof-of-work, a blockchain is **stripped of its distintive features and becomes a glorified database**.

## Explanation

1. Blockchain is simply a chain of data blocks containing more data within, where each block is linked to the previous one through cryptographic hashes. The true innovations lies **not** in this structure, but in how a network reaches consensus on the state of the ledger *(data block)*.

2. Dwork and Naor created a method called *Pricing Function*, which paved the way to what we call proof-of-work today. The paper describes this pricing function as a method to combat junk mail. Where the pricing function serves as the consensus mechanism. Proof-of-work requires participants to perfom computational tasks to add a new block, and therefore, making it economically infeasible to alter the blockchain's history.

3. Without proof-of-work, the blockchain loses its resistance to tampering. Why? Because in a proof-of-work system, altering the past block would require redoing the *"work"* for that block and all subsequent ones. And of course, as the blockchain grows, this malfeasance becomes more and more expensive.

4. Remove this computational barrier, and you're left with a design architecture where data can be change with relative ease, much like a traditional database.

5. Goes without saying, but I will say it anyways, that the absence of proof-of-work also eliminates the decentralized nature of creating blocks. Under proof-of-work, any participant can potentially add a new block to the chain by solving the computational task, ensuring a fair system. Without this, block creating can be controlled by a central party, effectively turning the blockchain into a permissioned database.

### Author

Norma Escobar
*nescobar@krpgroup.com*
