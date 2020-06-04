# Online gaming problems
The first chapter presented an outline of the meaning of a game and of a decentralised game. This chapter presents a brief outline of what an online game is and explores the problems of current online games. The major problems identified are important as decentralised blockchain gaming offers a solution to each.

## What modern online games got right
By default, all blockchain games are online games, although asynchronous and partially offline gameplay is possible it isn’t the main concern of blockchain game developers. Some of the most popular games today allow you to play alongside hundreds of other people in an online world. At the core of these games is the ability to be involved in shared experiences such as cooperative gameplay and storytelling.

Typical gameplay activities include:

* Players socialising and playing alongside each other: group activities and chat.
* Earning experience points to improve character abilities.
* Collecting and spending in-game currency.
* Collecting and purchasing items (including wearing such items).

Players playing with other players is really about social interaction and is a huge driver in the success of online games. Earning experience points to improve a player's character keeps players hooked and returning to the game. Collecting in-game items and participating in a game’s market economy is important for the same reason we have markets in the real world.

These activities make online gaming popular and why the industry has grown over the years, so these gameplay aspects should be kept in mind when building decentralised games. How can the experience of playing a current online game be recreated without the associated downsides? That is a question this book aims to answer.

The downsides are outlined in this chapter while later chapters explore the nuances of blockchain gaming technology to inform the reader of what’s possible and hopefully to enable better-informed design choices.

## Business case for online games
As a quick aside to the discussion on online games, it is worth noting that the games industry has increased in value over the last decade. Naturally, mobile gaming took off with the advent of smartphones, but desktop games are still proving popular and showing growth. While blockchain gaming on a mobile device is possible, playing a fully decentralised game is more difficult. Trade-offs are required to enable decentralised gaming on a device of limited computational resources.

In 2018, the global video games market was [valued at around $134.9bn](https://newzoo.com/insights/articles/newzoo-cuts-global-games-forecast-for-2018-to-134-9-billion/). While in 2019, it was [valued at $152.1bn](https://newzoo.com/products/reports/global-games-market-report/). Market research firm Newzoo expects this market to grow to [$198bn by 2022](https://newzoo.com/products/reports/global-games-market-report/).


## The main problems with online games
While online games are popular and show an expanding marketplace, there are several problems which ultimately lead to dissatisfaction because the players have limited influence over their own accounts, gaming assets, or the direction of the game that they play.

The main reason for the limit in influence is due to the centralised [client-server architecture](https://en.wikipedia.org/wiki/Client%E2%80%93server_model). Consequently, the relationship between the player base and developers could be summarised as “the players pay for the privilege of accessing the game”. The payments cover the costs of development (both initial and ongoing) and the costs of hosting the game servers.

It is only fair that developers earn money for their development efforts and can cover costs for hosting the servers. It is also fair for the company to make a profit and thrive. However, the nature of the relationship gives most of the power to the development team which seems unfair given that it is the players who are ultimately paying for the games.

This power dynamic that’s inherited from the architecture results in a few problems that blockchain can help to resolve. These problems will be explored in this chapter, but here is a list of the main problems with current online games that blockchain technology will help to resolve:

* Ownership of assets is poor in the current model of online games.
* Closed source leads to lock-in
* Action verification is weak and highly asynchronous.  
* Influence development (governance)


### Problems of ownership
The problem ownership in online games stems from the nature of the architecture. The relationship of the player’s computer to the server is mirrored in the relationship between the player and the development team.

Players pay to access the game, but all the game items (the assets) are held on the servers owned by the development team. The end-user license agreement (EULA) will likely point out that the [game items are not owned by the player](https://www.reuters.com/article/us-global-videogames-property-analysis-t/virtual-goldmine-in-game-goods-fuel-debate-over-digital-ownership-idUSKBN1Y0032). The artwork and the game code are traditionally under a [closed-source license](https://en.wikipedia.org/wiki/Proprietary_software) too.

While players are enjoying the game they are happy to play and be part of this relationship. However, when a player no longer wants to play, perhaps the wish to leave for some reason then there is a problem. Similarly, should the development company go bankrupt, the servers will disappear and all of the gaming assets and the players’ histories will disappear too.

This is a huge loss for players who spend hundreds or even thousands of hours participating in the gameplay of an online game. Moreover, players may also spend hundreds or even thousands of dollars purchasing game items from other players, but in most games this isn’t legal from the developer’s point of view. Players are often locked into the game with no way to reclaim the value they created.

To illustrate this risk it is worth to use a few real examples where players have spent thousands of dollars on gaming items.

#### Player Sells Virtual Resort for $635,000
An asteroid in the game Entropia Universe was originally purchased for $100,000. This was a Guinness World record at the time in 2006. Later the asteroid was split up and sold for a [total value of $635,000](https://www.prnewswire.com/news-releases/planet-calypso-player-sells-virtual-resort-for-63500000-usd-107426428.html).

These are the largest transactions ever seen in any online game and while they are large, they are still substantially less than the total value seen transacting across blockchain networks (which is a younger technology). The trust models are different, but it is clear that the less trust required the greater the transaction values can be.

#### Bloodbath of B-R5RB
This was a giant battle in EVE Online. In such battles, the spaceships are destroyed, which means the players incur real-world losses too. The estimated [real-world value of all losses was circa $300,000](https://www.engadget.com/2014-02-02-eve-evolved-the-bloodbath-of-b-r5rb.html). Interestingly, in traditional gaming architecture, the developers could undelete some or all of the lost items. Should they only recover some of the lost items then this could show bias.

The advent of blockchain technology in gaming will unlock this value for players by allowing true ownership. Although as pointed out in the first chapter, there is a nuance between the true ownership of tokens and of assets.


### Problem of closed source
Similar to the problem of ownership, the problem of being closed-source ([proprietary](https://en.wikipedia.org/wiki/Proprietary_software)) is an additional constraint. Even if players can trade their gaming items for real money, they are not able to do so when the developer goes bankrupt. This was established in the previous section. In addition, close-sourced licensing would prevent players from running their own servers legally or from modifying the game.

In the blockchain world, everything is open source and users can easily copy the code to run their network. This would also include the ability to legally make changes to the code. Game players have a long history of running custom servers with modified game rules. This is not necessarily due to nefarious desires, but it can be due to a gaming community that wishes to preserve what they have after the development team closes the official servers. 

Taking on technical hassle and legal risk is a rather large hurdle to overcome for many communities. In the process of trying to migrate from an official server to an unofficial server, it should be expected to lose many community members. Worst of all, players who split away are faced with losing all of their progress: they will lose items, experience points, quest/story progress. 

This could be different blockchain games where the full history of the game is public. A community could [fork](https://en.wikipedia.org/wiki/Fork_(software_development)) the code and the history to then launch their own separate network. This is the same as we see for [forks of current blockchain networks](https://en.wikipedia.org/wiki/Fork_(blockchain)).

Naturally, this leads to the topic of governance. If there is a split in the community there is generally a good reason for it. Players often feel ignored by the developers, they have limited influence in the current relationship model.

### Problem of influence and governance
Development companies run all of the servers and did all of the work to create the game and keep it maintained, so the question might be why should they cede any influence to the players?

Ultimately, it will be about money. While enough players like what the developers are doing they will keep paying their subscription fees. Players who get fed up will leave. This is a mild form of governance dubbed “voting with your wallet”. However, it seems like a blunt approach to governance which may not lead to the best outcome.

It is not uncommon for players to create a fuss on game forums about the direction of the game, but they may continue to pay anyway. Those that create the most fuss may not necessarily be the ones with the best ideas either. Developers should ensure that enough of the community is happy and don’t intend to leave anytime soon. Despite how easy that sounds, many online games have shut their servers because the game was unprofitable. To that extent, players never really own an online game, but rather pay for the privilege of accessing the game.

Bad management of the game's development leads to unhappy players and if that is not addressed quick enough then players will lease. Ultimately, leading to the demise of the game. This seems like a less than ideal outcome for all involved. The nature of the relationship needs to change such that players feel like they have greater ownership of the game: not just game items, but influence over the game’s direction.

The fans of blockchain networks (“hodlers”) are diehard fans with extreme loyalty. They feel a sense of ownership when they own tokens of the network. The community can also run servers to keep the network online. While they don’t have equity in the development company, they have a form of ‘skin in the game’. If the token price drops they will feel it. 

### Problem of action verification
The previous sections outlined the fact that online games are entirely reliant upon the development company. The relationship between players and developers is similar to that of the game’s architecture. However, this should be expected given what technology has been available hitherto.

It has been established that all game data had to be stored in centrally hosted databases, that includes player inventories but also player actions, which brings us to the last major problem.

Whenever players perform an action, the central database is updated to reflect the change in the player’s state. For example, when a new character is created the central database will be updated to reflect this change. Likewise, it will also be updated for players moving around in the game world, when items are traded, and when monsters are killed, and so on. These updates are analogous to the state transitions of blockchains.

While the current state of the game is stored centrally, the transitions are created within the client software installed on players’ computers. This requires a high level of trust from the developers to the players. The developers trust the players not to modify the client software and behave maliciously. 

If there is a lack of checks of the data sent to the database then players may find a way to duplicate items and currency, or even inject code which allows players to perform actions that are beyond what the game allows. Such cheating can include the ability to move through walls or fight with greater speed. Eventually, such actions can be detected after honest players report the abuse, or when developers perform consistency checks on the game data.

These are not new problems. Developers do get better at detecting malicious activity over-time but it would be better if the game could prevent them in the first place. This is one of the unique aspects of blockchain gaming: it may be possible to eliminate cheating entirely.

For a decentralised game that uses a blockchain the transactions, or rather players actions, will be broadcast across the blockchain network. Users who run the official game client can interpret the moves of all other players and determine if they are legitimate actions. Bad actions can be ignored, while valid actions will be recorded as state transitions.

This should eliminate within-protocol cheating, such as item duplication or code injection, but it will not eliminate out-of-protocol cheating. The latter could include botting or even simply lying to fellow community members. Blockchain technology will not be able to enforce all social contracts, so there is always an element of trust between players, however, if blockchain technology can eliminate item duplication (a double-spend) and eliminate invalid actions then it is already a huge step forward from what current online games can offer.


## References

What online games got right and their problems
* [Blockchain gaming: putting the state on-chain](https://medium.com/@edward.thomson/blockchain-gaming-putting-the-state-on-chain-cc3915090547)

Gaming trends
* [World trends of Video game industry](https://en.wikipedia.org/wiki/Video_game_industry#World_trends)
* [Global games forecast for 2018](https://newzoo.com/insights/articles/newzoo-cuts-global-games-forecast-for-2018-to-134-9-billion/)
* [Global games market report](https://newzoo.com/products/reports/global-games-market-report/)

Client-server architecture
* [System architecture of MMORPGs](https://en.wikipedia.org/wiki/Massively_multiplayer_online_role-playing_game#System_architecture)
* [Client–server model](https://en.wikipedia.org/wiki/Client%E2%80%93server_model)

Problems of ownership
* [Virtual goldmine: In-game goods fuel debate over digital ownership - Reuters](https://www.reuters.com/article/us-global-videogames-property-analysis-t/virtual-goldmine-in-game-goods-fuel-debate-over-digital-ownership-idUSKBN1Y0032)

Large Transactions
* [Planet Calypso Player Sells Virtual Resort for $635,000.00](https://www.prnewswire.com/news-releases/planet-calypso-player-sells-virtual-resort-for-63500000-usd-107426428.html)
* [Entropia Universe (Wikipedia)](https://en.wikipedia.org/wiki/Entropia_Universe)
* [Largest bitcoin transaction - Cointelegraph](https://cointelegraph.com/news/bitfinex-made-a-11-billion-btc-transaction-for-only-068)
* [Bloodbath of B-R5RB - Engadget](https://www.engadget.com/2014-02-02-eve-evolved-the-bloodbath-of-b-r5rb.html)
* [Bloodbath of B-R5RB (Wikipedia)](https://en.wikipedia.org/wiki/Bloodbath_of_B-R5RB)
* [Bloodbath of B-R5RB - eveonline](https://www.eveonline.com/article/the-bloodbath-of-b-r5rb)

Problem of closed source
* [Proprietary software (Wikipedia)](https://en.wikipedia.org/wiki/Proprietary_software))

Forking
* Fork (software development) - https://en.wikipedia.org/wiki/Fork_(software_development)
* Fork (blockchain) - https://en.wikipedia.org/wiki/Fork_(blockchain)
* Preserving gaming communities with blockchain technology - https://medium.com/@edward.thomson/fork-off-preserving-gaming-communities-with-blockchain-technology-4d90c04d0b8e

Action verification
* The Game Processor - https://github.com/xaya/xaya_tutorials/wiki/The-Game-Processor
* Libplanet design - https://docs.libplanet.io/0.5.3/articles/design.html
