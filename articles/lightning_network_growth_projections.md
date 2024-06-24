# Lightning Network: Analysis on Growth Projections

Please see workbook '3y-lightning-network-stats.xlsx' as reference.

## Precursors

1. The Lightning network is a system that allows for fast, low-cost transactions on top of the Bitcoin blockchain. It is a protocol that describes how these transactions should happen.

2. LND, Lightning Network Daemon, is one specific implementation of the Lightning network protocol. 

## Overview

**Understanding the principles:**

3. LND doesn't run its own full Bitcoin node; you need to configure it to connect to an existing Bitcoin node.

4. Everytime you run LND, you are running a full Lightning node.

    5. **Payments channel management:** you can open, manage, and close payment channels with other Lightning Network users.
    6. **Transaction Routing:** Your node can route transactions through the Lightning network, helping to find paths for payments between different users.

**Monetary incentive:**

7. By routing payments through your node, you can earn small fees from other users who use your node to send their payments.

## Lightning Service Provider (LSP)

8. An LSP is an entity on the Lightning network that offers various services to users and other nodes:

    9. **Liquidity provision:** provide liquidity by opening channels with users and other nodes, ensuring there are enough funds available to facilitate transactions.

    10. **Channel management:** manage payment channels, including opening, closing, and rebalancing channels to ensure smooth operation.

    11. **Routing**: LSPs often have well-connected nodes, making them efficient at routing payments through the network.

## Historical and projected growth rates

**To determine if the lightning network is growing, we will consider the following:**

12. Number of nodes
13. Number of channels
14. Network capacity
15. Development activity

#### Number of Nodes

16. Total # of nodes peaked in 2023, at roughly at 15,400. Currently, there is roughly 13,100 nodes. Extrapolating the historical data of 3 years, we calculated the daily average change to be 0.0293%.

#### Number of Channels

17. Total # of channels also peaked in 2023, at roughly 67,000. Currently, there is roughly 51,000 channels. Extrapolating the historical data of 3 years, we calculated the daily average change to be 0.0209%.

#### Network Capacity

18. No particular peak has been identified, The volumes from 2021 - 2023 are similar to current network capacity, which is 5,140 bitcoins. The daily average change we calculated is 0.1754%.

#### Development activity

19. Updates to LND, c-lightning, Eclair, and other implementations, as well as new applications and improvements are crucial in order to gain mass adoption. Most of these efforts are done by free-willing developers.

## Growth Analysis for LSPs - 365 days out

20. **Projected # of nodes:** Computing our daily average, we calculated that the total number of nodes will grow from 13,100 to approximately 14,500.

21. **Projected # of channels:** Computing our daily average, we calculated that the total number of channels will grow from 51,000 to approximately 55,000.

22. **Projected network capacity:** Computing our daily average, we calculated that the network capacity will grow from 5,140 bitcoins to approximately 9,700.

#### Implications

23. Our calculations are made based on optimistic scenarios. No macro-economic factors are being taken into consideration. This is a very simplistic model, that only takes into account the historical 3-year data we used as input.

24. While it appears that the network capacity is growing, it seems that the centralization of nodes on lightning is consolidating. It is very hard to determine if the node is operated by an entity that acts as an LSP, or if it's simply an individual.

## Conclusion

25. LSPs profitability is determined by the number of users who use their node to make payments. As of today, the Lightning network growth is conservative, some what stagnant. Using our daily averages, we can hypothesize that the projected number of nodes and channels will not surpass the peak of 2023 within the next year.









