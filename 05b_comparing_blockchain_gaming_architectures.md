# Comparing blockchain gaming architectures

## How to compare blockchain gaming architectures
Each architecture will be summarised in this section along with a brief discussion of their respective strengths and weaknesses. Under each architecture there is a quick summary that mentions the pros and cons of that particular approach plus there is a quick graphical summary provided too.

One quick method of comparing the differences of the architectures is to understand the key trade-offs that each offer, this is the so-called “pros and cons”. While these comments should be accurate and concise, a quicker way to compare the architectures is to compare the same key points and trade-offs in a graphical manner.

Blockchain gaming architecture can be viewed as a quadrilemma of:
* Decentralisation,
* Speed,
* Complexity,
* Massiveness (number of players).

<p align="center">
  <img src="/images/trilemma/Blockchain_Gaming_Architecture_Quadrilemma.png">
</p>

These are an inspired guess of the major points that are important for building a blockchain game. Each of these trade-offs need to be considered when choosing an architecture. In the long-run, it should be possible to have a solution that covers them all in a satisfactory way and we are seeing signs of that with the more advanced hybrid architectures.

**Decentralisation** is roughly about asking whether the official instance game be run on independent infrastructure and whether players own their own keys. If the game can survive, in theory, without the developer then it will have a high degree of decentralisation. Typically, this means higher redundancy to have great fault tolerance but likely means speed is lower, or complexity is lower for a given speed.

**Speed** is about the feel of the game and how close it is to real-time gameplay For a blockchain game there is a clear link to the number of transactions per second, although the two are not equivalent.

**Complexity** is about the number of game rules and their complexity. A complex game can always be implemented but it is likely to be slow.

**Massiveness** is about the number of possible concurrent players. Many blockchain games are aiming to be massively multiplayer and certainly blockchains can handle a great number of accounts, but it can come at the cost of speed. Game (“state”) channels can allow for real-time gameplay, but the number of players is low.

As many blockchain games focus on being massively multiplayer, then the last point can be ignored for many comparisons which reduces the quadrilemma to a trilemma (decentralisation, speed, complexity) and this seems like a sufficient basis for comparison.

## Monolithic: Pros / Cons
This approach guarantees decentralisation if the chain itself is decentralised. The security guarantees are therefore maximal, however this is also the “most heavy-weight” which is to say the hardest to scale. There is promising research in the area of rollups which may ultimately help all blockchain scale in terms of the number of transactions per second. While rollups could have the greatest impact on this architecture, it might still not be the best choice for larger and more complex games.

* **Pros**: maximal decentralisation and security.
* **Cons**: Poorest scaling properties, minimal complexity.

### Trilemma Comparison: Monolithic
<p align="center">
  <img src="/images/trilemma/Monolithic.png">
</p>

## Layered: Pros / Cons
This approach allows for strong decentralisation and greater complexity and scalability when compared to the monolithic approach. This architecture is a better choice for building a decentralised game without sacrificing the guarantees offered by the monolithic architecture; however, more work needs to be done to improve the speed of gameplay.

Users may potentially have to run 2 separate pieces of software (the blockchain node and the game binary) which could both be an irritation for players. It is possible to combine both pieces of software into a single file, but if there are multiple games that run on the same chain it would be more efficient to have players download the node software and sync it just once.

Downloading the same node software multiple times is inefficient, especially if it means downloading all of the block history again from the start.

* **Pros**: allows for strong decentralisation, improved complexity and scalability compared to monolithic architecture
* **Cons**: limited game speed compared to traditional online games, might require installing two separate pieces of software.

### Trilemma Comparison: Layered
<p align="center">
  <img src="/images/trilemma/Simple_Layered.png">
</p>


## Simple Hybrid: Pros / Cons
This approach is closer to the architecture seen in current online games. It has a familiarity that will make game developers feel comfortable as they learn about blockchain. The revenue model is better understood, while the addition of crypto-tokens may offer a way to augment that revenue stream.

This approach will undoubtedly offer the highest speed and has the least scaling issues from a blockchain point-of-view, but naturally it sacrifices decentralisation.

* **Pros**: speed, easier monetisation, well-understood architecture.
* **Cons**: can’t verify all player actions, limited decentralisation (and all the safety guarantees that come with it), potential vendor lock-in.

### Trilemma Comparison: Simple Hybrid
<p align="center">
  <img src="/images/trilemma/Simple_Hybrid.png">
</p>

## Advanced Hybrid: Pros / Cons
Fundamentally the architecture is decentralised, but it has the flexibility to allow players to connect to a centralised service such that the game installation is simple and no specialist knowledge is required to keep the blockchain in sync. On the other hand, the architecture allows players who want decentralisation to run all of the software on their machines.

Offering a centralised service can allow for low-powered devices to also play the game, this would include mobile phones and tablets.

This architecture won’t offer any improvements in terms of game complexity or speed, but it does provide the much-needed optionality that allows mobile players to take part in a fully decentralised game. Mobile players could run their own infrastructure in the cloud if they wish to eliminate trust issues.

* **Pros**: decentralisation is available, low-powered devices can participate.
* **Cons**: increased complexity of architecture so could be harder for developers but offers more options to the players.


### Trilemma Comparison: Advanced Hybrid
<p align="center">
  <img src="/images/trilemma/Advanced_Hybrid.png">
</p>

In the advanced hybrid model, games are decentralised so they will occupy the region labelled as "decentralised" in the triangle shown here. This architecture won't offer improvements in terms of this trilemma, as the limiting factors are the underlying decentralised aspect of the architecture.

However, it is now possible for devices to connect to a centralised service in order to reduce the hassle of the running your own infrastructure. This will reduce barriers to entry and hence boost user adoption rather. In the few games that employ an advanced hybrid architecture, it is essentially solving another problem. However, in the future there may be improvements made that tackle the trilemma presented here.

If a game with this hybrid architecture pushes non-critical parts of game play to a centralised, or even federated, infrastructure then that aspect of gameplay will feel similar to a traditional online game. For example, in Decentraland it is understood that player movement is not critical to gameplay therefore player movement does not need to be protected a blockchain. Consequently, player movement can be shown at a higher speed than with other fully decentralised games where movement must be protected by a blockchain.

Player movement is important for combat games, where the moves and positions of a player must be recorded on-chain in order to prevent cheating. Consequently, this results in slower combat with the current state of blockchain technology. There are potential solutions to this which will be considered in the chapter on scaling.

For comparison, games which are mostly centralised will occupy the lower region labelled respectively in the triangle.

## References

Blockchain Architecture Overview
1. [First Blockchain Architecture Overview](https://medium.com/@edward.thomson/the-thick-and-thin-of-blockhain-gaming-architectures-a51795156420)
1. [Trade-offs in blockchain gaming gaming](https://medium.com/@edward.thomson/trusted-trade-offs-in-blockchain-gaming-416faa5b8df8)

Quadrilemma of blockchain gaming architecture
1. [First mention of the quadrilemma](https://twitter.com/EAThomson/status/1246504051098955777)


