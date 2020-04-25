# Blockchain Gaming Architectures
## Introducing the architectures
There are 3 common architectural approaches for creating blockchain games. Each approach has a number of variations that naively create the appearance of a multitude of different architectures; however, all of the variations fit into 3 broad categories:

* Monolithic
* Layered
* Hybrid

The variations within each of these categories may be manifested from the difference in the way a blockchain is used as the base layer. For example, chains that provide smart contract capabilities may appear different than a simple chain that doesn’t offer smart contracts; however, the capabilities offered by a smart contract could easily be part of the functionality of the node software (sometimes referred to as “precompiled”). 

Simpler chains lack the generality that smart contract chains offer, however in the context of comparing architectures two different chains can be functionally symmetric. For a dedicated gaming chain, it may not be necessary to allow for the generality that smart contract chains offer.

## Monolithic
Typically: thick blockchain, thin game client
In this architecture the processing of the game logic is done entirely inside the blockchain client software. That is to say that the game logic is precompiled before the software is run.
All actions are stored on-chain and therefore such games can be fully decentralised, providing the underlying blockchain is decentralised. However, it is possible to run a permissioned and private blockchain network.

The user interface (UI), basically the game client, has two main functions: 
* render the data that’s recorded on-chain.
* allow the player to record new moves on-chain

The latter point means that the game client sends the player moves (“actions”) to the chain as transactions. Another way to see this is that the user interface is just a wallet. The node software determines if the received transactions and moves are valid: i.e. a correctly formatted and valid transaction, plus whether the move itself is legal.

As the node software is performing the validation and storing of all player moves then everyone who has a copy of the software and the chain data will be able to agree upon the game’s state. The current state of any game is the aggregation of all historical moves.

In this architecture, the game client (which includes the user interface) is thin while the blockchain is thick. All of the relevant computation is done on-chain such that the game client is lightweight and just needs to render the data without much interpretation.

The relative thickness of the blockchain software compared to the game client is a key characteristic for comparing the different architectures.

For games like poker or blackjack, they are simple enough that each blockchain client in the network could process all of the actions. Games of sufficient complexity, e.g. Chess, are unlikely to have their rules encoded into a smart contract for a general-purpose blockchain due to the cost of execution.

<p align="center">
  <img src="/images/architecture/Decentralised_Monolithic.png">
</p>
Figure 1. Decentralised monolithic: all game logic is processed at layer 1


The monolithic architecture scales poorly, so it will rarely make sense to put all of the game’s logic directly into the node software (aka the blockchain client). It is also too optimistic to expect the next generation of blockchains to hold a lot of complex game logic directly inside the node software since it most likely requires a lot of data to sit on-chain. Even if the logic is pre-compiled and packaged as part of the node software, rather than as smart contracts, it is unlikely to be enough of an efficiency gain.


### Example: Huntercoin
Huntercoin was essentially the first blockchain. It launched in 2014 and all of the game logic was coded directly into the chain’s software. All code is open source and available to view on GitHub.

As you should expect, a modified version of the game’s UI would allow for variations in graphics but it wouldn’t be allowed to modify the gameplay since all of the logic is on-chain.

#### Example: Nine Chronicles
This team is creating an MMO RPG game. It is essentially a turn-based 2D side-scroller. Gameplay includes crafting and combat.

The node software and game client came packaged together as a single binary. In the alpha and beta versions of the game, mining was performed by the development team but this should change for the future such that anyone can mine.

Similar to huntercoin, the Planetarium team who develop Nine Chronicles use a monolithic architecture but are looking to implement a  hybrid (decentralised) architecture in the future.

#### Example: Ethernal World
Ethernal World is a Roguelike game that is built entirely using smart contracts that run on an Ethereum sidechain. The map is generated as players discover the new rooms. Currently in alpha, the map is a grid of square rooms, but the content of the rooms is not known until a player first discovers them. One player action currently takes one block-time, as all actions are essentially transactions.

Current, gameplay allows for exploration of a huge map, PVE combat, and the finding of items and loot. In the future, the game will potentially have an infinite and enternally lasting world.


### Monolithic Variation: Smart Contracts
The most obvious variation of the monolithic model is to encapsulate the game rules inside a smart contract. The code for a smart contract is not known ahead of time so it is not precompiled. For chains such as Ethereum the logic of the smart contract can be arbitrarily complex, although greater complexity requires greater execution costs. As is known, Ethereum is a metered chain where each computation depletes some amount of fuel (“gas”).

<p align="center">
  <img src="/images/architecture/Decentralised_Monolithic_SC.png">
</p>
Figure 2. If the entire game fits inside a smart contract it is monolithic.


There aren’t many examples of this particular variant. Smart contracts are typically limited in their complexity so getting a full game into a set of contracts isn’t easy.

CryptoKitties almost fits with this architecture but doesn’t quite. Most of the game logic is done in a smart contract on Ethereum so the computation happens directly on-chain at layer 1, however, some of the processing of the game data is done off-chain which means that CryptoKitties has an additional layer, part of which is centralised. 

Given the relatively low complexity, the game could have been wholly decentralised and processed on-chain. There is a variation of the game called Substrate Kitties, which is a workshop created to teach people how to code for Parity’s Substrate framework.

## Layered
**Typically: thin blockchain, thick game client**


Blockchains by their design offer incredible fault tolerance, which is what makes them attractive, but not all of the game data need to be protected to the highest level. This suggests two possible solutions that revolve around deciding what is the most important data of a game should be recorded on-chain. The less important data, from a fault tolerance perspective, can either be derived or simply held off-chain.

Splitting up the data into layers also indicates that not all computation will be done on-chain (by the node software). There are two popular approaches to creating layers.

1. One solution to this is to put only the game assets on-chain but to keep all of the game’s logic off-chain. As the game logic is never on-chain it can be incredibly complex. In the games where the architecture is mostly centralised, the scaling limit will be similar for a traditional online multiplayer game. This is an approach that will be explored in the next section on hybrid architectures.

2. Another approach is to record all of the player actions on-chain but the node software doesn’t interpret those actions or verify the validity of their meaning. The transaction data will be broadcast across the network and, provided it was sent with the minimum fee, it will be recorded by all nodes (“on the blockchain”). This means that the base layer is essentially just a ledger: the node software is minimalistic and the computations are simple.

The latter solution is explored in the remainder of this section.

### Simple Layered (Decentralised)
In a simple layered architecture, players will run the node software and game client locally on their computer. The game client sits at a higher layer and reads the data from the chain.

The blockchain ensures that all players have the same record of player actions. Assuming that all players have the same game client then each player can independently interpret and verify which of the actions stored on-chain are valid. Consequently, all players can independently derive the current game state and the game can be correctly categorised as fully decentralised.

<p align="center">
  <img src="/images/architecture/Simple_Layered.png">
</p>
Figure 3. Decentralised layered: The game client contains the game logic but must read the on-chain data to function.



#### Multiple Clients, Multiple Games
The decoupling of the game logic from the node logic allows for greater complexity in the game rules. In addition, there can be multiple game clients as long as they interpret the on-chain data in the same way. The key point is to preserve the interpretation of the actions in order to derive the same game state.

Such a chain can also be used to host many games at once. The transactions for the different games can be marked in such a way to denote which game they belong to. The corresponding game clients will look for the respective transactions and interpret them accordingly.

It is also possible that the game client could be closed source too but that breaks the trust model and is contrary to the spirit of blockchain technology.



#### Example: Taurion 

The team behind Huntercoin have evolved their approach to gaming and no longer do monolithic chains. Taurion is a turn-based MMO RTS. Gameplay includes combat, harvesting, and making new buildings.

It runs on top of the Xaya chain which is a modified version of Namecoin. This means that it is a Proof-of-Work chain that also uses merge mining. It is co-secured with Bitcoin and mined by one of the larger mining pools (F2Pool).

While the chain stores all player actions next to their registered names, the software is lightweight since it doesn’t verify the player actions. The game client is where all player actions are verified: each player verifies the actions of every other player. The following diagram gives deeper insight into how their technology works.

<p align="center">
  <img src="/images/architecture/Xaya_architecture_detailed.png">
</p>

Figure 4: A detailed look at the Xaya architecture. The chain is layer 1, everything else is layer 2 (or higher).

Layers of the Xaya tech stack
* At the baselayer is a Namecoin-like blockchain.
* The API layer interacts with the node software to pull data from the chain.
* The Game State Processor (GSP) is the layer that interprets the actions recorded on the chain to determine if they were valid moves.
* The top layer is the user interface which renders the graphics in accordance to what the GSP shows and handles the users’ interactions. 

The Xaya team is currently working on advancing their architecture in such a way that players won’t have to run a full node, but can still play their games. Decentralisation is maintained for those who want it. This is important for mobile gaming as such devices won't be able to run either the node or the GSP, but they could connect to a trusted third party.

## Hybrid

**Typically: thin blockchain, thick game clien**

This architecture is also a layered approach except the upper-layers are split. Doing so provides an option of splitting the decentralised part of the stack from the centralised part. Splitting the stack is a common method that provides some amount of scalability or convenience. It is also possible to move the centralised part of the stack onto decentralised infrastructure which provides a progressive approach to achieving a goal of full decentralisation.

A well-designed game stack can incorporate a centralised option into an otherwise decentralised architecture.

There are two key types:

* Simple Hybrid—requires only a minimal amount of data on-chain. For example, using tokens to represent game assets and keeping most of the computation off-chain. As only asset representations are on-chain there is a requirement for centralised infrastructure to provide the enforcement of game rules.
* Advanced Hybrid—if a game can run in a fully decentralised manner, then it is possible to provide the optionality of running a centralised service for those users that desire such convenience while also providing the ability for other users to take the fully decentralised route.


### Simple Hybrid
In the simple hybrid model, the architecture is chosen such that only a minimal amount of data is committed on-chain. The most common usage of this architecture is to have the game assets represented by tokens. Consequently, the bulk of the game logic is processed off-chain in a manner that closely resembles the architecture we see in traditional online games.

Currently, this approach is the most common architecture for games that are labelled as “blockchain games”.

The game state will be stored on a central server run by the developers and requested by the game client when necessary. In theory, the speed of players actions should be equivalent to that of contemporary online games and gameplay should seamlessly integrate the on-chain data (e.g. tokens) such that performance is not affected.

<p align="center">
  <img src="/images/architecture/Simple_Hybrid.png">
</p>
Figure 5: Hybrid architecture: off-chain game client and UI is minimally coupled to the blockchain.

One contention here is that traditional games tend to be closed source, which differs from the spirit of blockchain technology. Developers may feel that this is favourable as it prevents the game from being easily copied. This comes with a well-tested revenue model that we see in current online games, so it is understandable that blockchain game developers may want to emulate this model.

The downside is that communities are locked into developer choices (as outlined in Chapter 2). Should a development company push the game in a bad direction the gamers are at their mercy. Many gaming communities try to reverse engineer closed-source code to break free from vendor lock-in, they won’t be able to clone the game state and preserve the progress their characters have made.

An open-source approach prevents vendor lock-in, but the centralised architecture prevents cloning the game state and prevents being able to independently verify the actions of all other players. The latter is the sacrifice paid to get better speed, but it is an important point for considering the meaning of ‘true ownership’.

If we demand our gaming assets to be truly ours then we need certainties about the assets seen in-game having a perfect and unambiguous one-to-one relationship to the tokens seen on the chain. Should a developer silently hand out free items to friends, this breaks the perfect one-to-one relationship and negates the key protection offered by blockchain technology. 

Similarly, should the developer become bankrupt then the game assets are irrecoverable, and the tokens held on-chain arguably lose their meaning.


#### Example: Forgotten Artifacts 
Forgotten Artifacts is described by its creator as “a hack-and-slash dungeon crawler which runs on Ethereum Mainnet via the Enjin Platform”. The first thing that should be apparent here is that the graphics and gameplay look like what you might expect from any modern online game.

For the most part, this game has a traditional client-server architecture, so it shouldn’t be a surprise that the look and feel of the game is comparable to other online games. This is in contrast to many other blockchain games where graphics are often described in a derisory way.

The game has been created using the framework, which also has an Enjin SDK plugin. This should make it easy to include Ethereum based assets within any Unity-based project. The result is that the game assets are stored centrally on the developer’s server, but also are represented as tokens on the Ethereum blockchain. This blend is centralisation and decentralisation illustrates why this architecture is a hybrid.


### Advanced Hybrid
One natural iteration of the simple hybrid model is to decentralise the centralised part of the architecture. The assets could be hosted on a decentralised-hosting technology, such as IPFS. Players who wish to make a copy of the game assets could do so and then subsequently host their own copy. The game developers could continue to host game assets on their own servers, but players would have the option of where to connect to.

Likewise, players can run full nodes if they prefer the decentralised trust model, but it would also be possible to use a mobile device and accept a centralised trust model. Players using a mobile device wouldn’t necessarily have to connect to a developer owned service though as the underlying architecture allows for a fully decentralised approach.

This is to say that the layered approach can work alongside the simple hybrid approach if the centralised part can also be performed in a decentralised way. This necessitates that the code is open source and that the architecture allows for a public network of nodes.

<p align="center">
  <img src="/images/architecture/Advanced_Hybrid.png">
</p>
Figure 6: Advanced hybrid architecture: game assets are stored off-chain but on a decentralised hosting solution.

#### Example: Decentraland
Decentraland launched in February 2020 and is one of the first games to feature blockchain technology as well as decentralised hosting and decentralised governance. This means that the community can operate their own blockchains nodes, content nodes, and participate in the governance of the network.

Code has been publicly released under the Apache 2.0 license and governance is actioned through the Aragon portal. The architecture appears similar to the simple hybrid mentioned above except the centralised part has been replaced with a decentralised hosting solution. This is where the game assets are stored. The assets are also “twinned” to tokens hosted on Ethereum.

While the game assets are stored in a decentralised way (e.g. the buildings and their attributes), it would seem that player movement is not stored on-chain. This is in contra-distinction to the Xaya games such as Taurion. At first sight, this may seem like a problem, but rather the nature of Decentraland means that fault-tolerant recording of player movement is not necessary.

It is understood that players don’t have to run their own Ethereum node or host their own gaming assets. This optionality of decentralised versus centralised suggests that Decentraland have a hybrid architecture.


#### Example: Taurion (advanced architecture)
Taurion was used as an example in the section for the “Simple Layered Architecture”. That was their architecture until early 2020. Due to the nature of that design it was only possible to run the game in a fully decentralised “mode” where players had to run their own blockchain node and run the Game State Processor (GSP)  too. The latter is the piece of software that processes all the player moves. Running both pieces of software requires a reasonably powerful device and so wouldn’t run on a mobile device.

After a series of upgrades to the architecture this year, it is now possible to run the blockchain node and the GSP remotely. In addition, multiple devices can be served from a single GSP node. This modification to the architecture provides optionality.

Players can still run a blockchain node and their own GSP on their desktop, or they could run that software in the cloud. In either case, they are a full node of the game. Players would also have the option of sharing their computational resources with friends, or they could perhaps provide a service to the community.

Naturally, the development team can run their own servers too that could be used by mobile gamers. Such players accept that they don't own the underlying servers and so sacrifice decentralisation, but they ultimately have the choice. The optionality provided by the Xaya team with their latest architecture is more appropriately described as a hybrid approach, but one that is more advanced than the simple hybrid approach that mimics the traditional online gaming architecture.

The Xaya team are providing this functionality as open-source libraries so in theory, any game developer could adopt their platform and immediately make use of these benefits.

<p align="center">
  <img src="/images/architecture/Hybrid_Xaya.png">
</p>
Figure 7: Xaya's latest architecture allows for optional decentralisation which allows for low-powered devices to play their games.

## References

Blockchain Architecture Overview
1.  [First Blockchain Architecture Overview](https://medium.com/@edward.thomson/the-thick-and-thin-of-blockhain-gaming-architectures-a51795156420)

Huntercoin
1. [Huntercoin Website](https://huntercoin.org)
1. [Huntercoin announcement (Bitcointalk)](https://bitcointalk.org/index.php?topic=435170.0)

Nine Chronicles
1. [Nine Chronicles Website](http://nine-chronicles.com/)
1. [Libplanet design](https://docs.libplanet.io/0.5.3/articles/design.html)
1. [Planetarium presenting on their architecture and game](https://www.youtube.com/watch?v=pBpxvnb8n5Y)

Ethernal World
1. [Ethernal World website](https://ethernal.world/)
1. [Ethernal team presenting on their architecture and game](https://www.youtube.com/watch?v=4bAwv3i28f4)

CryptoKitties
1. [Outline of problems with CryptoKitties](https://medium.com/loom-network/how-to-code-your-own-cryptokitties-style-game-on-ethereum-7c8ac86a4eb3)

Substrate Kitties
1. [Substrate Kitties Workshop](https://www.shawntabrizi.com/substrate-collectables-workshop/#/)

Taurion
1. [Taurion Website](https://taurion.io/)
1. [Xaya architecture, including description of the GSP](https://github.com/xaya/xaya_tutorials/wiki/The-Game-Processor)
1. [Xaya presenting on their architecture and games](https://www.youtube.com/watch?v=PNILIOkogUQ)
1. Architecture diagrams from private discussion with the Xaya team.


Forgotten Artifacts
1. [Forgotten Artifacts Website](https://forgottenartifacts.io/)
1. [Forgotten Artifact Tech Stack](https://blog.enjin.io/the-technology-stack-powering-forgotten-artifacts/)

Decentraland
1. [Decentraland Website](https://decentraland.org/)
1. [Decentraland Tech Stack](https://decentraland.org/blog/announcements/decentraland-next-steps-for-2020/)

