# Randomness, Determinism and Fault Tolerance

## Why do we need randomness?

Games require an element of randomness in order to have unpredictability. This creates risk and induces excitement in the player. It also allows for replayability: if a game can be defeated with the exact same actions each time then it will likely not be played a great multiple of times. This is why humans playing against humans can create a great level of excitement as humans appear more ‘random’ than computers.

Traditional games (non-online) can use a source of randomness that’s inside a player’s computer. For online games, the source of randomness is most likely to come from the game’s servers. However, in a blockchain setting both of these methods are problematic. 

Using a local source of randomness trusts players to be honest and not to tamper with their random values. When the rewards are high, the temptation will be too great for some players. Using the game servers as a source of randomness changes the point of trust from the players’ machines to the game servers, which are typically owned by the developers and represent a single point of failure.

Blockchains remove single points of trust and single points of failure. Users on the network are not trusted to be honest unless they can do so unequivocally with a cryptographic proof. Another way of framing this argument is that blockchains are Byzantine Fault Tolerant (BFT).

### Byzantine Fault Tolerance
A BFT protocol is one that works even if a small percentage of actors behave arbitrarily. The misbehaving nodes could be accidentally faulty or they could be malicious. Naturally, this assumes that the majority of actors are correctly following the protocol. The phrase was introduced in a research paper called “The Byzantine Generals Problem”. The titular problem concerns that of many actors finding consensus on 1-bit of information.

When consensus is found in a Byzantine Agreement algorithm, the result that’s agreed upon is guaranteed to be correct. This means that the agreed result can be thought of as deterministically correct rather than probabilistic. This occurs due because validators must vote upon the correctness of blocks. Once agreement is found upon a block, it becomes finalised such that transactions within that block cannot be reverted.

## Determinism
The fact that blockchains solve the Byzantine Generals Problem underlines the importance of determinism in blockchains. Each node in the Bitcoin network participates in the verification of transactions. For Ethereum that also includes smart contracts, so more general than transactions is the idea of an action.

For blockchain gaming, we might use a transaction to record a player’s action on a blockchain. This allows for distributed verification of game actions and hence provides a strong notion of fault tolerance. In game terms, this amounts to preventing cheating.

Therefore any game that aims to have distributed verification of actions will also need to have deterministic game rules. A system can have fully deterministic rules but the initial seed that is fed into the system can be random. If all nodes in the network have a copy of the same random number and all follow the same rules then they can agree upon the final result. This is a powerful property, but one that comes at a high cost of scaling.

## Collective Randomness
Seeding the deterministic functions of a blockchain game must be done in a way that is fair and transparent. Fairness requires removing as much bias as possible, removing single points of trust, and mitigating collusion.

As noted, players can’t be trusted to pick their own random numbers as they are most likely to pick results that are favourable to them. Generating randomness is difficult, even if doing that in a centralised manner, but relying upon a developer-run server requires trust and offers no guarantee that the number is bias-free.

These requirements suggest using a method for generating a random number in a collective manner such that no individual node or person can have outsized influence on the outcome. However, finding such a method has not proven an easy task and it is debateable whether this is a solved problem.

An old method that’s been around as long as Bitcoin is the use of the block hash as a source of randomness. This has a number of issues as outlined in the next section. Many of the newer chains (e.g. Ethereum 2.0, Polkadot, Cardano, Algorand) are tackling the problem head-on, but each of them has a different solution. Covering each of these solutions is out of scope for this book, but some details of the main ideas are included below.

For blockchain gaming teams it would be best to leave the creation of new mechanisms to the bigger teams who are actively researching and developing in this space. Fortunately, almost everything is open source and can be adapted to suit. 


### Block hashes
There is a great temptation to use block hashes as a source of randomness in blockchain games. The block hashes are naturally produced by running any blockchain and are collectively produced by design. However, the block producers have a lot of influence on the content of blocks and therefore have a lot of influence on the hash of the block.

Block producers could censor transactions from appearing in a block if the resulting hash is unfavourable, or the producer could simply withhold the hash entirely. This is a problem known as block withholding. 

Mixing hashes from several blocks can help to reduce bias, but this is still not considered a great solution.

For some circumstances it may be fine to use the block hash, such as for testing and proofs-of-concept. It may also be fine for games that have low-valued rewards; however, for any game aiming for high-value rewards, using the block hash is far from ideal.


### RANDAO
Given the difficulties associated with using block hashes, and given the general desire to have a collective source of randomness for many use cases, there is a strong desire for new methods of generating collective randomness. This area is a cutting edge of research in cryptography and while there is good progress, it is far from a solved problem.

In 2016, one team came up with the suggestion of RANDAO:

“A DAO (decentralised autonomous organisation) that anyone can participate in, and the random number is generated by all participants together! First of all, we need to create a RANDAO contract in the blockchain, which defines the participation rules.” - [Source](their github)

The main idea is always to have many participants contribute a random number and then mix those in a way that removes individual bias. The commitments should be public, but at the same time they shouldn’t be revealed until they need to be used. Additionally, there is a suggestion for improving the safety of the mechanism by confiscating the coins of bad actors.

The exact method of revealing and mixing those numbers is beyond the scope of this book. It should be noted that while the original suggestion was to be a smart contract, it is also possible to implement the mechanism within the software of the blockchain client.

RANDAO will be a component of the beacon chain in Ethereum 2.0 and will be augmented with a VDF. A brief overview of VDFs is in the next section.

#### Verifiable Delay Function 

A Verifiable Delay Function (VDF) is a function that requires sequential computation and is difficult to compute in parallel. However, verifying the result of the computation should be easy. Forcing a lot of sequential computation will take time and hence enforces a delay.

Requiring the property of easy to verify rules out the use of iterated hashing.

### Polkadot’s BABE algorithm
In Polkadot, the algorithm for producing blocks (BABE) requires the production of collective randomness. A detailed description of BABE is beyond the scope of this book. However, a quick recap of the scheme will be provided.

In BABE, blocks are produced by a pre-selected validator for a particular window of time. Selecting a validator means that they must produce a random number (an output from a VRF) that’s less than some target random value. This target value is produced by collective randomness.

Being a block producer can confer a lot of power to a single validator, who if chosen could censor transactions and try to double spend. This means that the method employed must not let validators choose the exact time that they desire, but the time given to them is random, and that the validator can’t be chosen repeatedly for many blocks in a row.

#### Verifiable random function
A verifiable random function (VRF) can be considered as a function that produces a cryptographically signed random number. This means that it is possible to publicly prove who created the random number: it is verifiable, hence the name. These functions by themselves do not provide collective randomness but rather provide the attestability which is useful for proof-of-stake networks where bad behaviour can be punished.



## Common problems with randomness in blockchain gaming
Assuming that a good method of randomness can be implemented there is still the consideration of how to use the random numbers correctly within a game.

In this section, a few known problems will be outlined with a comment on why they are relevant and there are suggested fixes on how to avoid them. For each problem there tends to be an algorithmic fix (i.e. a better way to use cryptography) but also a game design fix. In the latter cases, the design of the game’s mechanics is used to mitigate or mask the flaws of the underlying blockchain mechanisms.


### Problem: passive random values can be ignored
If the player passively obtains random values from the chain, then the player could ignore all hash numbers that lead to a bad outcome. Pulling these numbers from the chain can be done via a Remote Procedure Call (RPC) request. It is common for blockchains to have an RPC interface that allows users to query data stored on-chain via JSON RPC requests (Ethereum, Polkadot/Substrate) or via ZMQ (Bitcoin, Xaya).

Taking this data from the chain is not a transaction but simply querying for the data that exists on-chain. This means that querying the data is passive. If random numbers are taking in such a way then players can pull out a random number and perform the generation corresponding to that number without alerting anyone to the number they wish to use. That is to say, there is no commitment to using a particular random number.

It is natural that some random numbers (even let’s say block hashes) will likely have a worse outcome than others. Some numbers may lead to increased reward while others may lead to the character’s death. The problem here is not the generation of the random number, but the lack of commitment to using the number.

#### Fix: commit to unseen random values
There are two solutions here to this problem:

1. enforces a commitment to a particular outcome, or
1. enforces equality of outcomes.

The use of the word “commitment” here is not intended to be a cryptographic commitment, but rather the binding of an action to an outcome.

In the first case, the solution is to have the player sign a message (a transaction) that commits them to taking the next unseen random number. Moreover, the logic needs to be encoded in a way that prevents the player from taking a new random value. Recall that the actions that are generated from that random value should be deterministic.

The second solution requires smarter game design. Consider the distribution of rewards and the distribution of consequences and how they are affected by each possible random number. It may be possible to enforce the same rewards for each random number, such that no random number is better or worse than any other. 

Rather than making it a hard constraint, it is really a statistical constraint. There should be some variation in outcomes in order to allow for unpredictability: risk and reward should not be perfectly predictable. Try to enforce minima and maxima on enemy spawns, item spawns such as gold pieces or anything else. This is necessary for maintaining replayability of the game.

Consider a possible game where the player *could* pick their own random number. Given everything said above that would be unwise; however, if every random number leads to the same outcome, statistically, then it may not matter. It would likely be more important to ensure that the player uses a fresh random value each time such that they can’t force exactly the same outcome every time.


### Problem: Slow and expensive
While transactions give strong commitments it naturally incurs a communication overhead as well as a cost. Where possible, games should minimise the number of calls to the blockchain network. It is currently the slowest part of the tech stack.

On-chain randomness methods should provide strong safety guarantees but they tend to be slow relative to the speed of gaming. The maximum speed of RANDAO or BABE has not been well tested: the slow part is the coordination and mixing of the random values from each participant.

#### Fix: Derive pseudo-random values
Once a random value has been received in the game client, it could be acceptable to derive multiple values from the received value (e.g. with a hash function). The further derived values will not be truly random but can produce the illusion of randomness for a human player. This maintains determinism and reduces further costly transactions.

#### Fix(?): Off-chain sources of randomness
Game channels (“state channels”) let players in the channel determine a random value between themselves. It is fast to calculate since it is peer-to-peer (off-chain). Game channels lend themselves well to situations with a limited number of players. 

For games with a larger number of players then alternative solutions will be required: potentially decentralised oracles or some form of multi-party computation that’s computed off-chain but can be proven on-chain later. The latter may be faster than RANDAO or similar methods.


## References:

Byzantine Generals Problem
* [Byzantine Generals Problem](https://www.microsoft.com/en-us/research/publication/byzantine-generals-problem)

Consensus and Finality in blockchains
* [Consensus and Finality in blockchains](https://medium.com/polkadot-network/consensus-and-finality-in-blockchains-21b1f634fd00)

Block withholding
* [Game-Theoretic Randomness for Blockchain Games](https://arxiv.org/abs/1901.06285)

RANDAO
* [RANDAO: A DAO Working as RNG of Ethereum (First article)](https://steemit.com/ethereum/@darknet/randao-1-0-is-here-or-a-dao-working-as-rng-of-ethereum)
* [RANDAO on GitHub](https://github.com/randao/randao)
* [RANDAO on Eth Research](https://ethresear.ch/t/rng-exploitability-analysis-assuming-pure-randao-based-main-chain/1825)
* [RANDAO + VDF on Eth Research)](https://ethresear.ch/t/minimal-vdf-randomness-beacon/3566)

Verifiable Delay Functions (VDFs)
* [Introduction to Verifiable Delay Functions (VDFs)](https://blog.trailofbits.com/2018/10/12/introduction-to-verifiable-delay-functions-vdfs/)
* [VDF research](https://vdfresearch.org/)

Polkadot: BABE + VRFs
* [Polkadot learn randomness](https://wiki.polkadot.network/docs/en/learn-randomness)
* [VRF on Wikipedia](https://en.wikipedia.org/wiki/Verifiable_random_function)


