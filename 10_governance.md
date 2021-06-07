# Governance
A new topic that’s barely seen at all in traditional games is that of governance. The main reason for this is likely due to the lack of community input on the direction of game development. For offline games this is probably not a concern, however for online games where there is a shared experience it seems like a necessity.

Part of the reason that governance in traditional games is low is that the code is closed-source. The topic of governance is more common in open-source software, since the projects rely upon community efforts more than closed-source software.

For decentralised networks, where open source is the norm, the topic of governance is important. For decentralised games, concerns over the network are only part of the problem. In addition, there are concerns of the game development and also worth considering is the governance of player activity that’s normally found in the meta-game of traditional games.

In this chapter we cover the following topics:

  * Traditional Online Game Governance
  * Governance of Decentralised Games
    * Network / Chain Governance
    * Game Governance
    * Meta-game Governance

## Traditional Online Game Governance
Governance of online games hitherto has revolved around developers choosing the direction of game development with some feedback given from the community via forum discussions. Developers are free to listen to the advice or not. Naturally, there is something of an incentive to keep players happy and keep supporting the game. However, bad choices can break a game’s reputation to the point that it never recovers back to the point of it’s highest success.

It can be argued that too many bad development decisions has led to a large number of online games shutting down. Increased player participation in the governance of the game direction may help that, but would by no means be a guarantee of success. 

Developers should have a more holistic view of the game than an individual player. Often players want to make the game easier, but to the point where it could break the economy or balance of the game. This would be due to a small irritation in gameplay that if changed could break at a greater scale of the game. Otherwise said, player governance may not be the holy grail for sustainability but there are lessons to learn from traditional gaming governance as well as the governance of current blockchain projects.

One game that stands out as different is [Old School Runescape](https://oldschool.runescape.com/) (OSRS). The community complained that too much of the development in [Runescape 3](https://www.runescape.com/) (the newest version of the game) is done without player input. The player base was vocal on insisting that the developers of OSRS should listen to the community. The threat to the game here was that unhappy players would leave the game and so revenue would decline. This led to the creation of [polls](https://secure.runescape.com/m=poll/oldschool/).


Both games exist side-by-side and seem to be among the most popular online games, and both memberbases are happy with their respective governance styles. Runescape 3 has little player input (discussion does happen in the forums) while OSRS strongly relies upon player input. In order to have a new feature added to the game, the community must vote (in-game) and there must be a [supermajority of 75% voting “yes”](https://oldschool.runescape.wiki/w/Polls).

All accounts in OSRS can vote, although there is some mild Sybil-resistance by requiring a total skill count of 300 or above. Given the popularity of OSRS, it would seem that player governance can work and be successful. The question of “how much power should the community have?” might be the degree to which players can decide upon changes to the game.



## Governance of Decentralised Games
As mentioned in the opening paragraphs of this chapter, governance of a decentralised game can be split across three major themes:

  * Network / Chain Governance
  * Game Governance
  * Meta-game Governance

Each point of governance is important to consider, although the first two points may be the only relevant ones for a given game. Games that are simple may not have much scope for meta-gameplay such that the last point may not be relevant.

Network governance is relevant to decentralised games as they rely upon a blockchain network which may suffer from an exploit that could force the chain to rollback the state, or if a section of the community wishes to pursue their own direction they may ultimately wish to fork the code (and/or state).

Here we assume that a decentralised game is open-source and therefore governance of the tech stack is a necessary requirement.

### Network governance
The two most obvious examples of governance in the blockchain space are that of Bitcoin and Ethereum. Both projects follow a system of governance that can be described as *rough consensus* or *off-chain governance*. Simplistically, the community coordinates itself across social media (e.g. Twitter, Reddit), a variety of forums, and GitHub to discuss improvements and changes to the network.

Ultimately, propositions with the most apparent support can be drafted into an Improvement Proposal, the so-called [BIPs](https://github.com/bitcoin/bips) and [EIPs](https://eips.ethereum.org/EIPS/eip-1). These follow a similar methodology to the [Python Improvement Proposals](https://www.python.org/dev/peps/).

A more thorough discussion on Bitcoin’s governance can be found in Pierre Rochard’s blog [Bitcoin governance](https://pierre-rochard.medium.com/bitcoin-governance-37e86299470f). Below is an extract from this blog on what Bitcoin governance is. Ethereum follows a broadly similar style, although the details are not precisely the same.

**What is Bitcoin governance?**
> “Bitcoin governance is the process by which a set of transaction and block verification rules are decided upon, implemented, and enforced, such that individuals adopt these rules for verifying that payments they received in transactions and blocks fit their subjective definition of “Bitcoin”. If two or more individuals adopt the same set validation of rules, they form an inter-subjective social consensus of what “Bitcoin” is.”

Note that an element of on-chain signalling can occur as we see with Bitcoin mining pools adding some meta-data to a transaction to show their (dis)approval or a proposition. It would be remiss not to mention the possibility of on-chain governance that is possible with some blockchain tech stacks. See a later section for discussion.

The signalling from miners is not a binding enforcement of the changes. The community can still reject the proposal. In contrast, on-chain governance requires the community to vote on-chain and the mechanism is encoded into the node software such that changes can be implemented immediately upon passing.

### Game Governance
As a separate point from network governance, it is also important to consider how new developments to a decentralised game will be rolled out. It is possible to change gameplay features without ever updating the network part of the stack, and vice versa. That said, the two will most likely have an overlap with each other such that neither can be considered in isolation.

At the time of writing, few decentralised games exist, at least in the sense that we use the phrase. Both the [Xaya team](https://xaya.io/) and [Planetarium team](https://planetariumhq.com/) have signalled a preference to follow the rough-consensus method seen in Bitcoin and Ethereum. The Xaya team have roots in the early alt-coin days with Namecoin, so it is natural that they follow this path.

Nine Chronicles, the first game from Planetarium, now has [improvement proposals](https://github.com/planetarium/NCIPs/blob/main/NCIP/ncip-1.md) that draw heavily upon the process outlined by Bitcoin and Ethereum.

At present the NCIP process is actually focused on game development governance rather than network governance; however, the principles can be applied equally well to governance of the network part of the stack.

It is certainly possible for such games to implement a voting system similar to what exists in Old School Runescape (as mentioned previously).

#### Decentralised Autonomous Organisations
On Ethereum, it is possible to deploy a smart contract which has multiple signers who may control an amount of funds or otherwise coordinate voting upon a proposal. Such a loose-coordinate of people has been labelled as a Decentralised Autonomous Organisations, or DAO.

Present DAOs are like a hybrid of off-chain and on-chain. For updates to the code, this type of voting is similar to the signalling mentioned above (offchain), so the outcome of the vote is not forcibly binding by code. Contrariwise, the spending of the DAOs funds can be binding if this has been designed as such. The DAO would essentially be a multi-signature contract.

It is certainly possible for a decentralised game to be managed in such a way.

#### On-chain governance
On-chain governance is a way of formalising the governance of code that relates to the *runtime* of the blockchain node software. The idea is that changes to the network are performed on-chain, such that token holders must vote upon the changes in order for them to be enacted.

The changes to the network are proposed on-chain and are visible for inspection before being voted upon. This means that the changes are publicly available to everyone and can be immediately enacted once the voting has been resolved. Although not all of the node software will be easily placed into such a system, such that some parts of the code could rely on a hybrid of on- and off-chain governance.

In addition, it is possible for a network to have a treasury pot of funds that can be voted upon too. This suggests that blockchains that feature on-chain governance display similarities to that of the DAOs seen in Ethereum. Notable blockchains that use onchain governance are [Polkadot](https://wiki.polkadot.network/docs/en/learn-governance) and [Tezos](https://tezos.com/docs/learn/what-is-tezos).

On-chain governance can be applied in decentralised gaming too, provided the developer team has control over their software stack. It wouldn’t be easy to change core parts of Ethereum, but it is possible for a team to change their own stack.


### Meta-game governance
Metagaming concerns gameplay that exists outside of the rules encoded into the game itself.

Wikipedia provides a rough definition of [metagaming](https://en.wikipedia.org/wiki/Metagaming):

> Metagame is an approach to a game that transcends or operates outside of the prescribed rules of the game, uses external factors to affect the game, or goes beyond the supposed limits or environment set by the game.

This can also be described as [emergent gameplay](https://en.wikipedia.org/wiki/Emergent_gameplay).

To help illustrate this, we can consider a couple of examples:

  1. a game that has no built-in guild system does not mean that players cannot form guilds, but rather the guilds exist in the metagame.
  2. two players can issue a contract between each other for the delivery of items in the future at a price set now. This is a forward contract. Players are free to set up complex systems of trade beyond the game, however there is generally no formal support.
  3. a player shares their password with another player where both casually agree upon a payment for levelling services. Given the obvious risks of sharing passwords (account stealing), game developers ban accounts involved in such activity.

As these gameplay features exist outside of the game rules, they are beyond the purview of the control of the game developers. Should one player scam another then there is no recourse for the player who loses out, which is to say that traditional games have limited governance of the metagame.

Some game communities may see this element of risk as desirable (e.g. EVE Online); however, as decentralised games often concern items with real monetary value than the propensity for significant financial loss requires serious consideration to metagaming.

Otherwise said, a decentralised game can codify the social contract between players to be an actual codified contract (i.e. computationally enforceable). At which point the metagame is now a part of the codified logic of the game and arguably not outside the game.

While such features *can* be implemented within a traditional online game, there is less incentive to do so. This is an aspect of gaming that can easily be improved upon and done in a transparent way: players will feel greater trust of the underlying mechanisms whether the code is open source and there is a governance mechanism for resolving potentially exploitable gameplay mechanics.

One thesis here is that if decentralised protections can offer players greater safety then a greater monetary value will flow through the system.

#### Guilds as companies
Combining the ideas together, we could see a robust guild system in a decentralised game that allows for complex trading or financial contracts but with a great level of safety. In the paradigm of play-to-earn gaming, items in decentralised games can have real value. It is easy to see by logical induction that a guild performing activities in a game with real-value items is much like a real-world company. There would be nothing to stop this guild, basically a DAO, becoming recognised as an entity in the real-world.

This idea described in the blog [In game and on-chain: guilds can become companies](https://medium.com/@edward.thomson/in-game-and-on-chain-guilds-can-become-companies-4f10d7906b2e).


# References
  * [Old School Runescape](https://oldschool.runescape.com/)
  * [Runescape 3](https://www.runescape.com/)
  * [Polls - Old School Runescape Website](https://secure.runescape.com/m=poll/oldschool/)
  * [Polls - Old School Runescape Wiki](https://oldschool.runescape.wiki/w/Polls).


### Network governance
  * [BIPs](https://github.com/bitcoin/bips)
  * [EIPs](https://eips.ethereum.org/EIPS/eip-1)
  * [Python Improvement Proposals](https://www.python.org/dev/peps/)
  * [Bitcoin governance - Pierre Rochard](https://pierre-rochard.medium.com/bitcoin-governance-37e86299470f)


### Game Governance
  * [Xaya team](https://xaya.io/)
  * [Planetarium team](https://planetariumhq.com/)
  * [Nine Chronicles Improvement Proposals](https://github.com/planetarium/NCIPs/blob/main/NCIP/ncip-1.md) 

#### Decentralised Autonomous Organisations
  * [Decentralised Autonomous Organisations](https://en.wikipedia.org/wiki/Decentralized_autonomous_organization)

#### On-chain governance
  * [Polkadot](https://wiki.polkadot.network/docs/en/learn-governance)
  * [Tezos](https://tezos.com/docs/learn/what-is-tezos)


### Meta-game governance
  * [Metagaming](https://en.wikipedia.org/wiki/Metagaming):
  * [Emergent gameplay](https://en.wikipedia.org/wiki/Emergent_gameplay).

#### Guilds as companies
  * [Play-to-earn business model - Robert Hoogendoorn](https://www.playtoearn.online/whats-the-play-to-earn-business-model/)
  * [In game and on-chain: guilds can become companies](https://medium.com/@edward.thomson/in-game-and-on-chain-guilds-can-become-companies-4f10d7906b2e)
