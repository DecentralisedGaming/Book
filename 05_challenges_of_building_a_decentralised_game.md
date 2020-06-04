# Challenges of building a decentralised game
There are numerous challenges in building a decentralised game, many of them are of a technical nature, but as to be expected with cutting-edge technology there is also the human side which means that technological problems are also barriers for adoption.

The ultimate goal of decentralised gaming is to reproduce the complex online games that we already play, but to reproduce the architecture as one that’s decentralised. Some challenges apply to blockchain technology as a whole and not specifically to gaming as a use-case, while other challenges are likely idiosyncratic to gaming.

Reproducing the features we see in current online games with decentralised technology can even appear contradictory in nature. Blockchains are famous for providing a public ledger, but games require privacy for certain aspects of gameplay. Simply encrypting the data is not necessarily the answer, but there are other cryptographic mechanisms that may solve these problems.

On the human side, one important consideration is the design of the in-game economy, which is acknowledged as a hard problem as it relies upon predicting human behaviour. While this is not just a concern of a decentralised game, there are additional complications to consider.

If the game is autonomous, or perhaps even immutable, then the economy may break and be unfixable. However, as we see with any blockchain network, humans will find a way to fix the problem one way or another. This is a blockchain governance issue. In the past, governance has admittedly been messy but solutions do exist. Additionally, there is a related problem of updating the game’s software which may cause breaking changes to the game’s functionality.

For each of the challenges listed, possible solutions are offered too. A huge caveat here is that some solutions are the current best guesses rather than proven solutions. It is also worth pointing out that not all challenges have to be solved before a product can launch. The development team should keep the challenges in mind and plan to mitigate each issue, but finding perfect solutions won’t be necessary from the beginning.


## Determinism
To achieve the level of fault tolerance provided by blockchains they require that all nodes in the network eventually agree upon the history of transactions, or for decentralised games that all nodes eventually agree upon the full history of actions. This means that by necessity, blockchains must be deterministic and that the result of any calculation is the same regardless of the underlying hardware.

That’s not to say that randomness is not important, but rather we must have consensus on the result of an action. This presents an interesting problem for randomness, but this is left for a later chapter ([Randomness, determinism and fault tolerance](07_randomness_determinism_fault_tolerance.md)).

### Solution (Determinism)
Determinism is something of a ‘fact’ for decentralised games that use a blockchain as their ‘spine’. It has implications for architecture and implementation, but less for the game design. While it may be fine to have a reasonable degree of imprecision for current online games, it needs to be addressed explicitly in the implementation of any blockchain game.


## Economics and Autonomy
Designing and maintaining an in-game economy is one of the most important aspects of any online game. The importance is accentuated whenever the game is somewhat autonomous in nature as it might for anything that involves a blockchain.

Part of the problem is that upgrading blockchains is not as straight-forward as upgrading traditional software. There needs to be a more explicit level of social consensus that the upgrade will be accepted by the community. This is not seen in traditional game development.

If upgrades are difficult or infrequent, then making changes to the in-game economy could be more difficult and the developers will have a lessened role in directing how the economy evolves. More power will be in the hands of the community. For those that embrace blockchain this will be seen as a benefit, but it is definitely a challenge that needs consideration.

In addition, blockchain games tend to allow for easy real-world trading. This is seen as a benefit by many, but not all developers will be comfortable to allow this. It explicitly means that the real-world value of in-game items will have an impact on economic dynamics. 

On a related note, it requires consideration of how items and in-game currency is tokenised. The cryptocurrency that secures the chain may not be the same as the currency that’s spent in-game.

Solution (Economics and Autonomy)
The degree of autonomy and upgradeability is dependent on the architecture chosen and the level of decentralisation chosen. It is possible to upgrade a game where most of the computation is off-chain without affecting the need to change the underlying node software. However, users may still reject the upgrade.

Considerations of upgradeability and governance are outlined later in this chapter. Economics will be covered in its own chapter.


## Scalability
This is a notorious sticking point of blockchain technology and comes in multiple flavors, but ultimately means there are limits to the complexity and speed of game play.

Vertical scaling about the number of transactions per second, or in the context of gaming it is how many actions a single player can make in a second. 

While horizontal scaling is about concurrency, which is about how many players can be logged in at the same time, or the number of players who can make transactions at the same time. 

Blockchain technology is still immature with regards to both aspects, however efforts are being made to solve both. More details can be found in the chapter on scaling.

### Solution (Scalability)
Part of any scaling solution is to realise that most of the game logic must sit off-chain, but it must be done in such a way that decentralisation is not compromised. This allows blockchains to scale for a greater number of users at a faster rate of transactions per second, but it won’t quite allow for the scale that we are used to in current MMOs.

One possible solution for vertical scaling is the use of [game (state) channels](https://youtu.be/wMd9mvc8pqA?t=1414). This can allow for real-time transaction speeds, but only for a low number of players. For horizontal scaling possibilities include sharding and [zero-knowledge rollups](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/zk-rollups/).

Achieving high transactions per second for a large number of players concurrently will require additional advancements in blockchain technology. Potentially a hybrid solution that can combine a vertical scaling solution with a horizontal scaling solution.

As can be expected, there are often trade-offs between speed (actions per second), massiveness (number of concurrent players), complexity, and the amount of decentralisation. An overview of the architectural trade-offs are presented in Chapter 6 part b ([Comparing blockchain gaming architectures](06b_comparing_blockchain_gaming_architectures.md)), while an overview of scaling solutions is presented in a later chapter on scaling.

Additionally, clever game mechanics can hide delays to make them part of the experience. This allows weaknesses in technology to be hidden in such a way that players are not upset.


## Consensus and Finality
Gamers have an expectation of finality when playing a computer game. This notion is that once an action has occurred it cannot be reversed. In the context of an online game, one example would be when one player trades an item to another player for in-game currency. Both players have the expectation that the trade can’t be undone. Breaking that expectation is bad for user experience.

Traditional online games can offer this notion of finality as they only need to rely upon a single authority who dictates the reality. For a decentralised game, there is no central authority to dictate which actions are final.

The two most popular blockchain networks at the time of writing, Bitcoin and Ethereum, offer [probabilistic finality](https://medium.com/polkadot-network/consensus-and-finality-in-blockchains-21b1f634fd00). This means that actions can theoretically be reverted, as if they hadn’t happened in the first place. In practise, this hasn’t been a problem for Bitcoin or Etheruem; however, this probably cannot be assumed to be true of less popular blockchains that employ probabilistic finality. The reason for this lack of absolute finality is that the underlying consensus mechanism for both chains currently relies upon agreeing upon the longest chain.

Newer chains such as Polkadot, Tezos, Ethereum 2.0 will use consensus mechanisms that [guarantee absolute finality](https://medium.com/polkadot-network/consensus-and-finality-in-blockchains-21b1f634fd00). There are always caveats to such a strong statement, however there is a fundamental difference in the nature of the consensus mechanisms in these newer chains that replaces the “probabilistic” nature seen in the older blockchain networks.

An additional point here is the speed at which the networks reach consensus. This speed is reliant upon a number of factors. One is the speed at which data can be spread around the network such that enough nodes receive a copy of the player actions, but also the complexity of the consensus protocol and whether multiple phases of communication between nodes is necessary or not. The blocktime is a relevant concern, but fast block production doesn’t guarantee fast finality.

### Solution (Consensus and Finality)
There is likely a balance between having a fast block production time which is optimistic in its assumptions on finality, where the blocks are not yet finalised but are at least valid in their construction. This would allow for a separate consensus mechanism to “catch up later” at a slower pace but with the guarantee of absolute finality that players would expect.

A combination of a fast consensus mechanism to allow for rapidly recording player actions in addition to having the slightly slower finality mechanism is something that can be done with the [Polkadot tech stack](https://wiki.polkadot.network/docs/en/learn-consensus). It is a hybrid consensus mechanism.


## Upgrades
Historically, upgrading the node software of the blockchain has been difficult. Not because of the technical challenges with writing the code, but rather gaining the social consensus where participants of the network agree to download and use the updated code (see [Fork (blockchain) on Wikipedia](https://en.wikipedia.org/wiki/Fork_(blockchain)). The human side of upgrades will be under the section on governance later in this chapter.

For any decentralised application, the immutable nature of the data stored on a blockchain network presents a technical challenge. Once committed to the network, the idea is that this data cannot be changed. Naturally, this is a simplified representation but it is the crux of the problem.

On Ethereum, should a developer choose to [upgrade a smart contract](https://docs.openzeppelin.com/learn/upgrading-smart-contracts)
 then they have to deploy a new contract and ask users to migrate to the new contract. The old contract is immutable and cannot be changed. Certainly, changes *can* be the global state of accounts via governance, but this is an irregular state transition and not something that can be performed easily where the game developers have minimal influence upon the governance of the network.

This point on upgradability would apply to any decentralised game with a monolithic architecture. If the developers of the game are also the developers of the blockchain network then they will have a greater ability to influence the direction of development and make alterations to the network’s global state.

### Solution (Upgrades)
Taking the approach of a layered architecture (described in the [chapter on architecture](06_blockchain_gaming_architecture.md#layered)), where most of the game’s computation is off-chain, then greater flexibility is possible. Even if the data stored on-chain is immutable, the data can be tagged with different version numbers which allow the application to remain flexible. The full history changes to the software would still be public, but there would be no requirement to modify the blockchain node software.

Upgrading the blockchain node software stack is possible too, even while it is running, as we see in Polkadot.


## Privacy
In traditional online games we are used to having some amount of privacy. Some games allow us to choose whether our characters are shown as online to all other players, or just to those on our friends list.

The position of your character is only known to you and those who are standing nearby. The contents of your inventory and the amount of credits that you own are also hidden from other players. This is easy to achieve in a centralised game where all the data sits on the developers server and no one else can access it. However, as we repeat throughout this book: decentralisation is about removing privileged actors in order to increase trust in the system.

Hiding data on a blockchain where data is public is tricky.

### Solution (Privacy)
While Bitcoin and Ethereum offer mild pseudonymity with their addresses, ultimately the identity of many accounts is eventually leaked.

It is easy to suggest that using [Zero-knowledge proofs](https://en.wikipedia.org/wiki/Zero-knowledge_proof) can be used to hide the assets held by a player, but it will not be so easy to implement in practise especially if the desire is to scale the technology to thousands or even hundreds of thousands of users.

There are privacy coins that demonstrate privacy technology in production such as [ZCash](https://z.cash/technology/) or [Monero](https://web.getmonero.org/resources/moneropedia/ringsignatures.html), but that still doesn’t mean the translation to a gaming use-case will be straight forward.

Can there be some other commit-reveal mechanism? Perhaps but again, it is not entirely clear how this can be implemented. There needs to be a full consideration of resource harvesting, as well NPC spawns and loot drops.

Addressing privacy in decentralised games will feature later in a chapter dedicated to the topic.


## Incentivising node hosting
One benefit of a decentralised network is that the developer does not need to be the only entity to run the game servers. A key aspect of a decentralised network is that many people will participate by running the software. This has the benefit of allowing players to sync data from other players which should reduce some costs for the development team.

A natural consequence is that this relies upon players being willing to run the software. If players are keen on the idea of decentralisation then they may be altruistic in their desire to support the network by running a node; however, it cannot be assumed that all players will want to run a node. 
If there is a lack of people to run the software then the network will not be sufficiently decentralised. One hope to boost the attractiveness of running a node is to find a solution to incentivise people to run the software; however, this is not yet a fully solved problem.

### Solution (Incentivising node hosting)
The best efforts so far have been seen in the [Sia](https://sia.tech/technology) and [Filecoin](https://docs.filecoin.io/introduction/what-is-filecoin/) projects. Replicating the methods employed in these projects may offer viable approaches.


## Undesirable messages / user content
Some of the key tenets of blockchain technology are privacy and censorship-resistance. Privacy being about concealing personal identities, and also considering anonymity, while censorship-resistance is about an “anything goes attitude” to content.

This leads to challenges in how to handle spam messages, content that people may find offensive, or even illegal content featuring in chat messages. 

### Solution (Undesirable messages / user content)
The underlying blockchains of any decentralised game use fees as ensuring that all spam has to be paid for. The data that’s inserted directly on-chain does not need to appear in the game either, so even if offensive messages are inserted as comments into a transaction those comments don’t need to be shown inside a game, although they could be viewed in a block explorer or anyone who choses pull data directly from the chain.

The in-game chat channels can use other decentralised protocols as storing messages on-chain would be slow and expensive. In order to make the game attractive and minimise offensive messages, the chat system mechanic could allow players to optionally subscribe to different channels. The developers could run a centralised chat channel that’s free from offensive discussion; however, players could subscribe to a community run channel where the rules are relaxed.


## Bots
As blockchains are censorship-resistant (or permissionless) in nature, then there does not tend to be a notion of blocking or banning accounts from interacting with the network. While players should pay a fee to register their actions on-chain, there would not be any mechanism to prevent players from automating their actions. In almost all online games this is seen as undesirable.

This is one of the main reasons that it is challenging to build a multiplayer PVE game that runs “on the blockchain”. The Xaya team found that their original project, [Huntercoin](http://huntercoin.org/), was filled mainly with bot accounts.

### Solution (Bots)
There are multiple potential solutions, but no single guaranteed solution to work for this issue.

Player-vs-player combat is one method that can allow for humans to outsmart and kill accounts which are bots; however, bots don’t need to sleep so it does not seem likely that PVPers will be able to catch and eliminate all bot activity.

Another potential solution is to design the game mechanics in such a way that bots are lured into particularly simple tasks which are repetitive and perhaps profitable, but otherwise boring for humans. This means that there is an acceptance of bot accounts, but that they are somehow useful to the game rather than a hindrance. This is a so-called honeypot approach.

It is also possible that the game could be moderated via a DAO where accounts are blocked via a voting process. However, this may lead to cartels forming and bringing new problems.


## Oracles (Data sources)
If a game requires off-chain data it should be accurate and attestable. Ideally, there wouldn’t be a single point of failure either, but it depends on what the data is and how it is being used. Taking real-world data for use in a game, is different from taking data from a single player who has performed some computation off-chain.

In the context of blockchain technology, typically the [oracle problem](https://medium.com/@teexofficial/what-are-oracles-smart-contracts-the-oracle-problem-911f16821b53) is seen as that of putting real-world data on-chain, but the [problem set is actually wider](https://en.wikipedia.org/wiki/Oracle_machine).

### Solution (Oracles)
The best well known teams working on the decentralised oracle problem are [Chainlink](https://docs.chain.link/docs/what-is-chainlink) and [Provable](https://provable.xyz/) (previously Oraclize). Their algorithm or something similar seems like a good candidate for solving this issue.


##  Usability
One of the most important points of gaming is providing software that’s easy to use and widely accessible. Dealing with current blockchain technology presents multiple hurdles and results in a poor user experience. Some of the problems already mentioned feed into user experience, and usability, already. Not all usability issues will be included here, but a few of the main topics will be mentioned.

Blockchain technology is seen as slow compared to the centralised technology that we are used to. Given that the technology is so new and complex, it is not easy for newcomers to understand why blockchain technology might be slow or difficult to use. This is a user experience that’s at odds with what people expect from games.

To be a “full participant” in a decentralised network requires the node soft and managing private keys. This could be in addition to installing the game client too. Running a full node on a mobile device is seen as undesirable or not possible given the limited computing power.

Blockchain networks require a fee to be charged per transaction to prevent spam but this incurs a problem of allowing a free-to-play solution for a decentralised game.

### Solution (Usability)
There are multiple problems here so there cannot be a single solution.

Public blockchain nodes can be deployed that allow users to remotely connect to them. This will remove some inconvenience for new players and can also allow for mobile devices to participate in decentralised gaming. Naturally, such a service will likely incur a fee.

Node software could also be packaged into the game client executable, although that won’t be efficient for a chain that hosts multiple games.

The free-to-play problem is an interesting concern and could be solvable in some way that allows a limited amount of functionality. Suggestions for this topic will appear in a later chapter.


## Account management
One of the advantages of blockchain technology listed was that of fault tolerance. That is part of the reason why the technology can be trusted with billions of dollars; however, it also requires the use of cryptographic keys. It can be well argued that they provide a stronger notion of security than a password but managing keys forces a certain level of complication that is beyond the average computer user (See Chapter 4 of the [Mastering Bitcoin Book](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch04.asciidoc)).

The current user experience of managing keys in the current blockchain ecosystem is not particularly user friendly. Not only do keys need to be stored securely, but they need to be password protected and should be backed up. 

For most web services, losing a password is not necessarily a terrible outcome as accounts can typically be recovered via a “forgot password” function. Losing a private key often means the complete loss of coins associated with that key, such a loss in the context of a computer game would be a terrible user experience.

### Solution (Account management)
A fully custodial service can alleviate many of the problems associated with kay management; however, that is against the spirit of decentralisation. Having a full custodial service should be one option, but not the only option.

[Ethernal](https://ethernal.world/), which runs in the browser, made use of the web wallet [Portis](https://www.portis.io/). The wallet was fully integrated with the game meaning that a user didn’t have to install separate software. This allows for far easier user on-boarding. 

Using the Portis wallet only requires remembering a password and according to the whitepaper the company does not have access to the users’ coins. However, it does not seem possible to fully verify this. For new users this seems like a good balance of trust and ease of use, but for higher value accounts it may be necessary to pursue alternatives.

A decentralised social recovery mechanism is also possible too, although this is still something that seems to be in the early phases of use.


## Governance
As described under “Upgrades” in the previous section, upgrading blockchain software has historically relied upon finding informal social consensus. Bitcoin and Ethereum take this approach of rough consensus (see this [overview on off-chain governance](https://docs.ethhub.io/ethereum-basics/governance/#what-is-off-chain-governance), where the community discusses improvement proposals and attempts to come to consensus in an informal way.

The developers of the node software need to feel confident that the upgrades they make will be accepted, so generally they are slow to make upgrades which are contentious and would make the updated software incompatible with previous versions.

As all software is open source then all changes can be inspected and tested by the community. When a large enough portion of the community disagree with an upgrade then there may be a split within the community when a sub-group decides to “fork” away and create a new network. This can be seen as both a benefit as well as a challenge.

It is too early to say how similar these challenges will be for decentralised games. It could be that gamers, particularly from a non-blockchain background may care less about the details of the upgrades as long as the game functions. However, it is also too early to rule out the possibility that this could be a huge topic of concern for any decentralised game.

### Solution (Governance)
Embracing the culture of forking is one of the few ways to embrace blockchain technology. It is inevitable and something of a challenge to gain comfort with. Planned forks are really upgrades that the community agree upon, while communities that split away have found that forked chains had less value than the original chain. This is mainly due to the costs of switching from one chain to another despite the open-source nature of the code.

It would be remiss not to mention there is another form of blockchain governance called “[on-chain governance](https://wiki.polkadot.network/docs/en/learn-governance)” where votes upon software upgrades are recorded on-chain and the outcome of the vote is enforced across all nodes at the same time. Such a mechanism provides a formal way of recording votes and providing a conclusion to any proposal.


## Standards
While standards are about a technical specification, the convergence to a common set of standards would make development easier, but this is in essence an issue of human coordination and social consensus.

Both Bitcoin and Ethereum have their respective improvement processes ([BIP](https://github.com/bitcoin/bips) and [EIP](https://eips.ethereum.org/all)), which are both focussed on arriving at a practical end goal of common pieces of code that can be widely used by the whole community. These efforts are successful in achieving practical social consensus, even if they are not perfect.

In relation to gaming, the Ethereum community has the [ERC-20](https://eips.ethereum.org/EIPS/eip-20), [721](https://eips.ethereum.org/EIPS/eip-721), and [1155](https://eips.ethereum.org/EIPS/eip-1155) standards which are all useful in their own way to blockchain gaming and worthy of consideration for use on other blockchain networks.

Other organisations have also tried to create standards, such as the Ethereum Enterprise Alliance, but it would seem that their efforts have been fairly muted by comparison.

### Solution (Standards)
Following already established standards that are deployed on existing blockchain networks (like the ERCs mentioned) is probably the best way to start. Deviations in an implementation make sense when it solves a practical problem, but adding yet another standard without implementing the code won’t be a worthwhile pursuit.


## Funding
The cryptocurrency space is famous for its [Initial Coin Offering](https://en.wikipedia.org/wiki/Initial_coin_offering) (ICO) method of funding open-source software. In brief, teams sold tokens and received money in order to build their products. While raising money in an ICO is an initial way to seed development of the game, it doesn’t provide sustainable revenue. Raising money via an ICO is similar to raising money via Kickstarter or Indiegogo.

Once a traditional came has launched, the development team can continue to ask for funds, but once a blockchain network has launched, it isn’t possible for the developer to raise new funds by issuing new tokens. Developers are not supposed to have unmitigated power to simply create new tokens out of thin air. This also makes subscriptions tricky, as it isn’t possible for the developer to simply issue no tokens for money received.

Typically, blockchain networks have a known rate of issuance or at least in the case of Ethereum where the issuance is dynamic it isn’t seen as acceptable to sell new tokens as this would require a hardfork and would likely cause dissent within the community. 

### Solution (Funding)
Creating open-source software does not mean no value is created, or can’t be retained, it just is not obvious if we only consider traditional business models. Recently, there was a [blog published by a16z](https://a16z.com/2020/04/08/crypto-network-effects/) that essentially describes why blockchain projects can have a proper business model. 

That’s not to say this is a solved problem, but there are a number of possibilities available which will also feature in a later chapter dedicated to funding decentralised games.

In the cryptocurrency space, we have seen that [ZCash team](https://medium.com/@colinbaird_51123/on-the-future-of-zcash-funding-c6e5d3fd50d8) raise funds by taking some percentage of the new tokens issued in each block. This was an explicit part of the design and is implicitly agreed upon by those who use their network or buy their tokens.

In the decentralised gaming space, the [Xaya team](https://github.com/xaya/xaya_tutorials/wiki/First-steps#chi-powers-the-xaya-blockchain) have taken a different approach where they take a percentage fee of all transactions.

The ZCash method is hardcoded into the node software, while the Xaya method is essentially optional although it is part of the official software. Both methods provide an income stream to the respective teams in their native tokens; however, given the volatility in cryptocurrency prices this is not a guaranteed business model.

This suggests that alternative models may be desireable. There is a way for decentralised games to offer centralised services which provide an amount of convenience. This could be around custody or remote data access to a blockchain node for players who don't want to run a blockchain node. Both may generate revenue for the developers but both depart from the spirit of decentralisation.


##  Regulations
Blockchain and cryptocurrency regulations are still in a grey zone for most countries. The exact legal status is not always clear or well understood and in many cases there are negative connotations for projects related to cryptocurrencies. This is seen as undesirable for many companies wishing to enter the industry.

The full range of regulatory issues goes far beyond the scope of this book which is mostly technical in nature.

### Solution (Regulations)
This is not something that can be fixed in the short-term. Some jurisdictions are friendlier than others, so picking a friendlier jurisdiction is probably one of the few solutions available.

## Integration with existing game engines
Perhaps something of a minor issue, but for any chain to be successful as a gaming blockchain that intends to host multiple games from many different teams then the process of building a game for that chain should be as easy as possible.

### Solution (Integration with existing game engines)
Making life easy for game developers is to provide integrations with the popular game engines such as Unity and Unreal. This is something already seen with teams working the decentralised gaming space.

Xaya have games running on their chain built from both Unity and Unreal; however, there are no real restrictions on language used provided a game is built to interface via JSON RPC.

The [Planetarium](https://github.com/planetarium/libplanet) team has worked exclusively in Unity (C#). The [Enjin team](https://enjin.io/product/platform), while not yet working on fully decentralised gaming, have built plugins for Unity and Godot.


# References

Overview of of challenges in decentralised gaming
* [Blockchain Gaming Unconference in Paris 2020](
https://medium.com/web3foundation/blockchain-gaming-unconference-outcomes-51dfca561801)

Scalability
* [Video of Daniel Kraft from Xaya on Game Channels](https://youtu.be/wMd9mvc8pqA?t=1414)
* [Explanation of game channels for Xayaships](https://github.com/xaya/libxayagame/blob/master/ships/README.md)
* [Game Channels for Trustless Off-Chain Interactions in Decentralized Virtual Worlds](http://www.ledgerjournal.org/ojs/ledger/article/view/15)
* [Summary of zero-knowledge rollups](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/zk-rollups/).
* [Matter Labs on their ZK-Rollups framework](https://medium.com/matter-labs/introducing-zk-sync-the-missing-link-to-mass-adoption-of-ethereum-14c9cea83f58)

Consensus and Finality
* [From Bitcoin to Polkadot: A brief history of consensus and finality in blockchains](https://medium.com/polkadot-network/consensus-and-finality-in-blockchains-21b1f634fd00)
* Brief explainer on consensus, finality and [Polkadot’s hybrid consensus mechanism](https://wiki.polkadot.network/docs/en/learn-consensus)

Upgrades
* [Fork (blockchain (Wikipedia))](https://en.wikipedia.org/wiki/Fork_(blockchain))
* [Upgrading Smart Contracts (Ethereum)](https://docs.openzeppelin.com/learn/upgrading-smart-contracts)
* [On-chain governance in the Polkadot tech stack](https://wiki.polkadot.network/docs/en/learn-governance)

Privacy
* [Zero-knowledge proof (Wikipedia)](https://en.wikipedia.org/wiki/Zero-knowledge_proof)
* [Zero-Knowledge Proofs Reading List](https://zkp.science/)
* [Explanation of the technology behind ZCash](https://z.cash/technology/)
* [Ring signatures in Monero](https://web.getmonero.org/resources/moneropedia/ringsignatures.html) 

Incentivising node hosting
* [Brief overview of Sia](https://sia.tech/technology)
* [Brief overview of Filecoin](https://docs.filecoin.io/introduction/what-is-filecoin/) 

Bots
* [Huntercoin](http://huntercoin.org/)

Oracles
* [Overview of Oracle problem in blockchain](https://medium.com/@teexofficial/what-are-oracles-smart-contracts-the-oracle-problem-911f16821b53)
* [General overview of Oracles in computing (Wikipedia)](https://en.wikipedia.org/wiki/Oracle_machine)
* [What is Chainlink](https://docs.chain.link/docs/what-is-chainlink)
* [Provable.xyz](https://provable.xyz/)

Account Management
* An overview of keys and address in Bitcoin from Chapter 4 of the [Mastering Bitcoin Book](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch04.asciidoc)
* [Portis](https://www.portis.io/)

Governance
* [Fork (blockchain) (Wikipedia)](https://en.wikipedia.org/wiki/Fork_(blockchain))
* [Overview of off-chain governance](https://docs.ethhub.io/ethereum-basics/governance/#what-is-off-chain-governance)
* [On-chain governance in the Polkadot tech stack](https://wiki.polkadot.network/docs/en/learn-governance)


Standards
* [Bitcoin BIPs](https://github.com/bitcoin/bips)
* [Bitcoin BIPs explanation](https://en.bitcoin.it/wiki/Bitcoin_Improvement_Proposals)
* [Ethereum EIPs](https://eips.ethereum.org/all)
* [ERC-20](https://eips.ethereum.org/EIPS/eip-20),
* [ERC-721](https://eips.ethereum.org/EIPS/eip-721),
* [ERC-1155](https://eips.ethereum.org/EIPS/eip-1155)

Funding
* [Initial Coin Offering](https://en.wikipedia.org/wiki/Initial_coin_offering)
* [ZCash Funding (discussion on 29% fee)](https://medium.com/@colinbaird_51123/on-the-future-of-zcash-funding-c6e5d3fd50d8)
* [Zcash Funding going forward from October 2019](https://zips.z.cash/zip-1014)
* [Xaya team on-going funding](https://github.com/xaya/xaya_tutorials/wiki/First-steps#chi-powers-the-xaya-blockchain)
* Value of open-source blockchain networks, [Crypto’s Business Model](https://a16z.com/2020/04/08/crypto-network-effects/)


Integration with existing game engines
* [Xaya documentation](https://github.com/xaya/xaya_tutorials/wiki)
* [Planetarium use Unity](https://github.com/planetarium/libplanet) 
* [Enjin integrations - Unity and Godot](https://enjin.io/product/platform)

