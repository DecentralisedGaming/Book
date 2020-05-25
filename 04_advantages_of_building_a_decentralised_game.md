# Advantages of building a decentralised game

[Chapter 2](https://github.com/DecentralisedGaming/Book/blob/master/02_online_gaming_problems.md) outlined the main problems with modern online games at a high level. These broad themes covered a multitude of smaller and more nuanced problems. The list was never going to be exhaustive but rather it covered the main areas that blockchain game developers could help to solve.

This chapter will take a more granulated look at the advantages offered by blockchain technology and its relevance to decentralised gaming. As this technology is at the cutting edge, there are still many unknowns such that the stated advantages here are based upon our expectations of how the technology works plus what we see working in current blockchain networks.

One of the biggest selling points of blockchain technology is the fault tolerance it offers. Restated another way: blockchain technology excels in solving problems of trust. This is a fortuitous coincidence as the main problems highlighted in Chapter 2 were chiefly problems of trust.

Not all problems of current online games are about trust, and fortunately there are further advantages offered by blockchain technology that are not based on solving trust-based issues.

As such, the presentation of advantages will be split into those based on trust and those which are not. As always, it is important to keep in mind that not all games that leverage blockchain technology are decentralised, so many of the advantages here would not apply to such games. The main focus here is on decentralised games rather than games that simply feature a blockchain for holding tokens.

## Advantages based upon trust

### Anti-cheating
 In a decentralised game the blockchain provides guarantees on the ordering of the transactions it receives and then protects that history such that it is immutable. When transactions are accepted by all nodes, and hence consensus is found, there are strong guarantees on the correctness of the history of transactions.

This is possible because of the strong notion of fault tolerance that blockchains offer. As Bitcoin provided a practical solution to the Byzantine Generals Problem it provided a notion of anti-cheating for money. It isn’t possible to double-spend bitcoins or create new ones in a way that contradicts the protocol.

Moving from Bitcoin to a more general blockchain for gaming involves translating “transactions” to “player actions” and hence arrive at the notion of anti-cheating in gaming. As the history of all actions is public, and the source code is public too, then essentially any player can check the actions of any other player. Actions that contradict the protocol can be ignored.

Hacking the front-end game client to inject code, as with a traditional online game, should have less effect and perhaps no effect for a decentralised game that’s backed by a blockchain. 

The benefits here are that all players are on an equal footing from the perspective of the protocol, and consequently developers spend less of their time trying to detect and fix cheating after it has occurred.

The inherent trust in Bitcoin has enabled a single transaction over a billion US dollars in April 2020. By comparison, the largest sales in centralised online games are acknowledged to be for the Planet Calypso resort in Project Entropia (total value of all transactions: $635,000).

### Unstoppable
By implication of using a blockchain there is a high degree of redundancy. One consequence of this is that the networks may be hard to shut down and pseudo-autonomous. This provides a measure of certainty on knowing that the chain may always exist despite the lead development team going bankrupt, and consequently provide comfort to the community that the game will continue to be online.

### Transparent economics
As already mentioned, blockchain code is open source and the history of transactions is public. The corresponding code for the games that run on top of the chain should also be open source in order to fully provide the notion of decentralisation. 

The guarantee here is not that the economic model is correct, but rather that it is transparent. The benefit to such transparency is that the creation of all game money can be traced and determined whether it follows protocol or not. 

The creation of all money should follow protocol under the assumption of a working blockchain network. All players can independently check that no money has been silently printed and pushed into the game perhaps to the benefit of favoured players. It is a form of anti-cheating in relation to in-game economics.



While this has some negative impact on privacy, which may be solved by the use of an appropriate privacy scheme, it does mean that the economics of the chain is transparent.

### Provenance
The transparent economics that allows for the public verification of the supply of money also allows for the public verification of item creation. The provenance of all items are public from the day of creation until the day they are destroyed.

Otherwise stated, decentralised games provide their respective gaming communities with the assurance of provably fair item acquisition. Re-stated once more, all players are on an equal footing with regards to the protocol in terms of item acquisition and transfer.

### True ownership
The most lauded property of blockchain games is that of true ownership; however, as it expounded through-out this book tokens that reside upon a blockchain are not intrinsically the same as assets found within a game. If a blockchain game is run on a central server, but with tokens “glued” on to the tech stack, then it is fallible to all the problems of current online games. The notion of true ownership would only apply to the tokens and not the game assets.

For decentralised games, the assets as well as the tokens would be truly owned by the players. This is possible as the game tokens tied to a player's private key. Unless that key is stolen it is computationally infeasible to steal the tokens without tricking the player. 

To provide the additional guarantee on the ownership of the assets, over-and-above the ownership of tokens, the game assets must be part of an open-source game with a transparent economy with high-fault tolerance. Just as bitcoins cannot be stolen without first obtaining a private key, game assets can not be stolen without first stealing a private key.

This has not been possible with traditional games where assets are owned by the development teams and often it is impossible to trade these items for real money. Decentralised games provide the benefit of allowing players to trade their items as they please.

Given the strong notion of ownership offered by Bitcoin is not a surprise that the total value of the network is valued in billions. Depending on the point at which the price is taken, Bitcoin alone can have a greater market capitalisation than the entire gaming industry.

### Censorship resistance
One property of a decentralised blockchain is that no node is given preference over any other. A consequence is that no participant who makes a transaction is necessarily given preference over another. There is a caveat here which is that typically transactions with higher fees are accepted in preference to those with lower fees; however, there are no other criteria for filtering out a transaction of a sufficiently decentralised network.

In the context of gaming this means that players can submit their actions to the chain regardless of any personal dislike that a developer may have of a particular player. While this is beneficial to players in the sense that it removes one possible angle for developer favouritism, it can also bring challenges in relation to spam.

An interesting nuance is that while the blockchain itself is censorship-resistant, it *can* be possible to build censorship into the games that run on top of them. This means that moderation is possible at the game level while allowing the chain to remain censorship-resistant.

### Permissionless
Is another name for censorship resistance. One additional point is that multiple games can run on top of a public chain. Each game can be deployed without first seeking the approval of the chain’s developers.

This is a benefit to new game developers who want to deploy a decentralised game but don’t want to build and run their own infrastructure.


## Advantages not based upon trust
The advantages of blockchain technology are well established in the domain of trust, but what’s less clear is where they provide advantages in other domains. The following list of advantages may appear speculative but each point is not unfounded.


### Easier Multiplayer Coordination
Blockchains naturally allow for thousands of accounts to be created and recognised as valid. This property can be extended to decentralised games that are linked to a blockchain network address.

This won’t enable the most efficient means of coordinating players for every circumstance, but it provides a base layer that doesn’t need to be reimplemented for every new game. It allows players to use the same address across multiple games which is the starting point for allowing a possible blockchain game **metaverse**.

### Reduced hosting costs / Incentivised hosting
A blockchain network is assumed to be run by a community of participants who each carry some burden in running the network. This should be beneficial for developers as they can reduce the costs associated with running powerful servers.

Ideally, players are incentivised to run nodes too. There have been a number of efforts made here to enable incentivised hosting, but none of these networks have yet reached the levels of adoption necessary to deem their method successful. 


### Reduced bandwidth costs
An additional consequence of reduced hosting costs is that of reduced bandwidth requirements placed upon the development team. Players will be able to sync their nodes and game states with other players.

In the past, using torrent links instead of direct downloads has been a popular option for many developers in the past. That also provides an avenue for decreasing bandwidth costs which is independent of blockchain networks, but is a fair example of using a decentralised network to reduce costs. 

Steam is also another possibility here for traditional game developers, although that necessarily meant giving up a portion of income.


### Easier fundraising
This benefit applies to any “blockchain game”. Selling tokens allows for fundraising from a wide base of people was a highly popular method in 2017. The most common method was called the Initial Token Offering (ICO), although a number of variants also exist. ICOs and related variants allowed for fast fundraising in combination with building up a base of interested customers.

In the years since (2018, 2019, and 2020) has seen a decrease in the market cap of all blockchain products and consequently a reduced interest in fundraising via token issuance.

### Player loyalty
Players who own tokens may feel like they have a greater sense of ownership of the game and therefore have greater loyalty. This could be applicable to any blockchain game.

### Player governance
Governance of decentralised games is ultimately enacted via forking, which comes in two flavours: rough consensus and on-chain governance.

For rough consensus, the code maintainers implement what they believe are the desires of their community.

On-chain Governance is conducted via token voting and the changes are enforced once the voting period has concluded. This requires increased complexity of the chain, but it guarantees that players have a direct influence on the game. Typically, the weights of votes are in accordance with the number of tokens any given player owns.

Should some sub-community decide that they no longer agree with the overall development direction, then it would be possible for them to create a whole new chain via a hardfork. In doing so they would copy the code and run a new network with their desired parameters. This is possible with fully decentralised games where the assets are also open for the community to reuse.


### Community preservation via forking
Leading directly on from the previous subsection on governance. A community can create a new network and a new instance of the game if all the code and the assets are open for reuse. This is possible for decentralised games that use blockchain technology.

The benefit is that the history of player progress is public and can be preserved. The new network and game would essentially be a seamless continuation of the previous game. This allows any sub-community to avoid changes they believe will severely affect their game experience.


## Summary list of advantages

### Advantages based upon trust
* **Anti-cheating**
* **Unstoppable**
* **Transparent economics**
* **Provenance**
* **True ownership**
* **Censorship resistance** 
* **Permissionless**


### Advantages not based upon trust
* **Easier Multiplayer Coordination**
* **Reduced hosting costs / Incentivised hosting**
* **Easier fundraising**
* **Player loyalty**
* **Player governance** 
*  **Community preservation via forking**

## References

Advantages of blockchain in gaming
* [The opportunity” (a brief overview of advantages)](https://www.theblockcrypto.com/post/34646/blockchain-gaming-part-i-the-opportunity)
* [How blockchain is making digital gaming better](https://www.ibm.com/blogs/blockchain/2020/02/how-blockchain-is-making-digital-gaming-better/)
* [Blockchain Gaming: The Good, the Bad, the Ugly, And All Their Intersections](https://hackernoon.com/blockchain-gaming-the-good-the-bad-and-the-ugly-h1d92g6k)

Consensus and Byzantine Generals Problem
* [From Bitcoin to Polkadot: A brief history of consensus and finality in blockchains](https://medium.com/polkadot-network/consensus-and-finality-in-blockchains-21b1f634fd00)

Advantages of blockchain technology
* [Top five blockchain benefits transforming your industry](https://www.ibm.com/blogs/blockchain/2018/02/top-five-blockchain-benefits-transforming-your-industry/)
* [The Benefits Of Applying Blockchain Technology In Any Industry](https://www.forbes.com/sites/ilkerkoksal/2019/10/23/the-benefits-of-applying-blockchain-technology-in-any-industry/)
* [Improving Customer Retention And Loyalty Programs With Blockchain](https://www.forbes.com/sites/forbestechcouncil/2020/04/29/improving-customer-retention-and-loyalty-programs-with-blockchain/)

Large Transactions
* [Planet Calypso Player Sells Virtual Resort for $635,000.00](https://www.prnewswire.com/news-releases/planet-calypso-player-sells-virtual-resort-for-63500000-usd-107426428.html)
* [Largest bitcoin transaction](https://cointelegraph.com/news/bitfinex-made-a-11-billion-btc-transaction-for-only-068)

Gaming trends
* [Total value of gaming industry 2018](https://newzoo.com/insights/articles/newzoo-cuts-global-games-forecast-for-2018-to-134-9-billion/)
* [Total value of gaming industry (latest values)](https://newzoo.com/products/reports/global-games-market-report/)

Forking
* [Fork (software development)](https://en.wikipedia.org/wiki/Fork_(software_development))
* [Fork (blockchain)](https://en.wikipedia.org/wiki/Fork_(blockchain))
* [Preserving gaming communities with blockchain technology](https://medium.com/@edward.thomson/fork-off-preserving-gaming-communities-with-blockchain-technology-4d90c04d0b8e)

