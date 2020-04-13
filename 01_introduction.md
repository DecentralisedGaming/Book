# Introduction

## The promise
Back in 2017, the cryptocurrency prices surged to an all-time high, bitcoin went north of $20,000 and ether above $1,000 per token. During the mania of rising prices, a new funding model for open-source software (OSS) came to the forefront: the Initial Coin Offering (ICO). While there were earlier ICOs, 2017 was the year when they came to prominence with quite a few projects raising over $100 million each. 

The frictionless ease with which to raise money was a boon to OSS funding, but this euphoria of fundraising encouraged lazy due diligence. Many projects who raised funds in this period will never deliver on their promises.  However, the ICO model should not be discarded because of poor practices seen during 2017. The ease-of-funding that ICOs brought was something that was sorely needed.

This increase in funding to OSS has also raised the profile of game development teams operating in this niche industry called “blockchain”. Linking computer games to electronic money was already possible (online games have their own currencies) and so a natural step was to link computer games to cryptocurrencies. Often all games that are linked to cryptocurrencies are lumped together and called “blockchain games” although the reality is more nuanced as will be explored in this book.

The first question newcomers will ask is “why?”. Why should computer games be linked to blockchains? Blockchain games offer the promise of true ownership, where players can demonstrate that their gaming assets are under their control with strong cryptographic guarantees. Assets can be represented by tokens on a blockchain and the ownership of such tokens is provable to anyone in a public manner.

Not only can ownership be easily proven, but blockchain technology enforces a set of rules that prevents the tokens from being stolen. This is the first promise of blockchain gaming. However, a more complicated reality is found upon digging deeper. There is a nuance in the narrative of true ownership: owning a token is not the same as owning an asset. While a blockchain can enforce true ownership of a token, it does not inherently enforce the true ownership of an asset.

The suggestion that a player owns the underlying gaming asset has some underlying assumptions which can be broken when the game is not decentralised. Should a blockchain game have its assets stored on a central server then those assets disappear when the server disappears. The tokens by themself are like a twin, but one that’s arguably meaningless when the assets disappear. This highlights that true ownership of tokens is not the same as true ownership of assets. 

This nuance can be solved by moving to a decentralised architecture. However, in these nascent days of blockchain gaming, the solution also bears a cost. This book will make a positive case for building blockchain games that preserve true ownership of assets by suggesting that blockchain gaming should be decentralised.

Beyond fundraising and true ownership, there are also new possibilities that are unique to blockchain. The technology enables distributed action verification that promises to eliminate cheating, the history of gaming worlds can be forked and preserved even if the developers decide to shutter their servers.

This book will explore the various design choices that blockchain game developers can employ along with their relative strengths and weaknesses. Every design choice has an accompanying trade-off, but smart game design choices can offset some of the weaknesses.

The intention is that a better understanding of these design choices will lead to better blockchain games. We shouldn't lose sight of the fact that game development is about building games. So what do we mean by games? What are they and how does blockchain fit in? This chapter provides a simplified explanation to both of those questions.


## What is gaming?
Games should be fun. That's why we play them. The best games are also engaging and memorable. There may not be a universal definition of fun and the sensation of fun will vary over time, but fundamentally the main design principle in building a game is to make them enjoyable.

As a point of comparison, the following is taken from the "Game" article on Wikipedia:

"A game is a structured form of play, usually undertaken for enjoyment and sometimes used as an educational tool. Games are distinct from work, which is usually carried out for remuneration, and from art, which is more often an expression of aesthetic or ideological elements. However, the distinction is not clear-cut, and many games are also considered to be work (such as professional players of spectator sports or games) or art (such as jigsaw puzzles or games involving an artistic layout such as Mahjong, solitaire, or some video games)."
[Source](https://en.wikipedia.org/wiki/Game)

This is a general description of a game and does not distinguish between video games and non-electronic games. What was true in the past should still be true now and well into the future regardless of the medium by which games are played.

As an additional point of reference, here are the opening lines to the Video Game article on Wikipedia:

"A video game is an electronic game that involves interaction with a user interface to generate visual feedback on a two- or three-dimensional video display device such as a touchscreen, virtual reality headset or monitor/TV set. Since the 1980s, video games have become an increasingly important part of the entertainment industry, and whether they are also a form of art is a matter of dispute." - [Source](https://en.wikipedia.org/wiki/Video_game)

Through-out this book the use of "computer game" will be used instead of "Video game".

## What are decentralised games?
You might expect the first word here to be "blockchain"; however, before getting to that explanation, it is worth trying to understand what is meant by a decentralised game.

Naturally, we inherit the definition of a game from the previous section then consider the necessary requirements to fulfil for some definition of decentralisation.

Any game that features distributed planning and authority, and is designed to resist single points of failure could be described as "decentralised". In this book, the usage of the phrase “decentralised game” will refer almost exclusively to games that require a computer or similar electronic device.

Let's explore with an example.

### Example: Chess
Would play-by-mail chess fit with the definition of a decentralised game? Probably. What about chess played using a website or software? Maybe, but there are more questions here. Play-by-mail is decentralised since there is no requirement for a central planner and the games are 1 versus 1. If playing by email then disputes are about whether a move was sent and an opponent claimed not to receive it. Dispute resolution is not ideal and matches are likely to be abandoned. The lack of good dispute resolution makes such a game a poor choice for including monetary reward.

In theory, using a web server to record the chess moves should mean that players can't pretend they didn't receive another player's moves; however, this still requires trusting the server which is likely run by a trusted third-party. The history of moves could be public such that members of the chess community could monitor for foul play such that bad players and bad game servers will receive a negative reputation for incorrect behaviour.

A big problem arises in the case where the trusted party misbehaves as remediation is difficult. While a web server may seem to better enforce the rules of the game it introduces centralisation. Ideally, there would be no requirement for privileged parties in the exchange and recording of moves as well as no privileged parties for handling dispute resolution. The suggestion is that decentralised enforcement of rules would provide a fairer and more robust game, but there is a cost.

Building decentralised software is harder than building centralised software. The extra effort in development necessitates that there must be additional requirements for doing so. Stated another way, for games of little monetary value building a decentralised version is unnecessary. If there is no money at risk then a centralised architecture is likely acceptable. 

## Design requirements of a decentralised game
What do we require from a decentralised design that necessitates the additional development effort?

Decentralised software should:

* Remove the need for trusted intermediaries.
* Minimise the number of privileged actors.
* Minimise single points of failure.
* Provide resiliency against errors and faults.
* Ensure correct behaviour of participants in the network.

None of these points pre-suppose the use of a blockchain; however, blockchain technology is the optimal solution for certain problems: those that require minimising trust.

## What is a blockchain?
While this book assumes knowledge of blockchain technology, it is worth recapping a basic definition as a point of clarity. There are differing definitions and differing levels of purity.

“A blockchain is a growing list of records, called blocks, that are linked using cryptography.” - [Source](https://en.wikipedia.org/wiki/Blockchain)

This list is a chronological record of all transactions (changes in a ledger). Cryptographic signatures prove who made the transaction while cryptographic checksums ensure that errors can be detected. The transaction records are publicly available over a peer-to-peer network, although creating a private network is also possible. 

The most important feature in a blockchain network is the consensus mechanism. The nodes within the network must agree upon the history of transactions. The set of rules encoded within the software guarantees all nodes agree upon a single version of this history.

When exchanging messages across a public network it is essential to use cryptography. The ability to unequivocally determine which address sent a transaction, via a cryptographic signature, is a requirement for sending a transaction across a public network. What made Bitcoin unique is that it solved the ability to prevent double-spending in a decentralised manner.




## What are blockchain games?
Blockchain games are a subset of decentralised games that make use of blockchain technology. The main reason for using a blockchain is to minimise the amount of trust required in other actors within the network. The result should be improved trust among network participants who are most likely to be the players.

While blockchain can be used to create a decentralised game, that isn’t yet the most popular strategy employed. The addition of a blockchain within a software stack does not guarantee decentralisation as will become clearer in the chapter on the common architectures found in blockchain games.

These are the main ways in which blockchains are currently used in gaming:

* Initial Coin Offering: a crowdsale of tokens to raise funds for development.
* In-game payment tokens: the ability to purchase game assets with a native token.
* Non-Fungible Tokens (NFTs): provide the ability to uniquely track game items and ensure that the items are distinct from each other.
* To maintain a record of actions (also referred to as moves): this enables a transparent economy and prevents cheating.

The last point is unique to blockchain technology and underpins decentralised action verification. This is the ability to prevent cheating by ensuring that all participants must follow the same set of rules. If all players have a full set of actions of every other player then it will be possible to distinguish which attempted actions are valid and which are not.

Beyond what is shown in the above list, there are new features and functionality which are only possible in a decentralised game:

* Games owned and governed by the players (via a DAO).
* Gaming guilds can be DAOs with a treasury and perhaps even a legal structure (e.g. a mutual or a company etc).
* Forking game communities to preserve character histories.
* A reduction in hosting and bandwidth costs for the development should the network become decentralised.
* Censorship resistance
* Permissionless innovation

## Summary
In this chapter, there was an overview of what a game is and outlined some reasons as to why we might want to make a game decentralised, as well as outline the potential benefits of using a blockchain. While these should sound like obvious benefits, there also a cost in adding complexity.

There needs to be a good reason to consider the additional hassle of working with blockchain technology. The benefits will be clearer after looking at the problems with existing games. The next chapter will provide a deeper dive on this topic.
