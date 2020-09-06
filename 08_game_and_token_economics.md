# Game and token economics
Designing and maintaining an in-game economy is one of the most important aspects of any online game. We can’t give a perfect picture of how an in-game economy should be managed, but we will identify the important factors that have the biggest impact on gaming economies.

This chapter will provide a summary of what has worked for traditional online games then consider how to apply that to decentralised games. However, there are additional unique factors and challenges to take into consideration, of which the most important is chain security. For any blockchain, miners and validators are rewarded for providing their security services. It is expected that almost decentralised games will have a real-world trading aspect to them 

A central theme for this chapter is the concept of supply and demand, as well as the lifecycle of game assets (how they are used or transformed). This is a big concern for game design of contemporary online games, but the economic principles that apply to current games will also apply to decentralised games.

An interesting question that comes up frequently on gaming forums is whether an online game can have a free market. That is, a market that’s purely driven by players and has no external influence. This is a well-debated topic for real and virtual economies alikes. One additional factor for games is that developers need to set the dispersion and extraction rates of resources, in the real world we have no control over the dispersion of natural resources only on improving our ability to extract them. This means that game developers have god-like powers in setting up the economy. This additional factor makes it harder to balance a game economy, even if it is simpler than a real economy.

On balancing an economy, one overlooked point is fundraising via crowdfunding. This is a typical method for launching blockchain projects, or indie games, but selling items in order to raise funds means that the fundraising round is intrinsically linked to the games’ economics. Some crowdfunding campaigns sold limited edition items as a way to entice greater amounts of funding. While limited-run items can go up in value over time, so appear attractive during a fundraising round, the total amount of items sold can have a long term impact on the in-game economics.
While fundraising is an important factor, the details of fundraising and a comparison of such methods will be the subject of the next chapter. Each of the aforementioned aspects will be explored in this chapter.

## Traditional Game Economics
The in-game economies of current online have been studied in an academic context and as well commented on by various gaming outlets over the years. The aim of this chapter is not to provide a comprehensive overview of past work, but a summary of key information is provided.
For clarity, let’s start with a quick definition of a virtual economy:

> “A virtual economy is an emergent economy existing in a virtual world, usually exchanging virtual goods in the context of an online game, particularly in massively multiplayer online games (MMOs). People enter these virtual economies for recreation and entertainment rather than necessity, which means that virtual economies lack the aspects of a real economy that are not considered to be "fun" (for instance, avatars in a virtual economy often do not need to buy food in order to survive, and usually do not have any biological needs at all). However, some people do interact with virtual economies for "real" economic benefit.” - [Virtual Economy (Wikipedia)](https://en.wikipedia.org/wiki/Virtual_economy)

Virtual economies are interesting as they mimic the characteristics of the real world economy. Offline games will have a simple economic loop where items discovered in game will have a fixed (or least predictable) buying and selling price. Anderson presents the idea of core economic loop to describe an offline game in the following piece: [Economic Research On MMORPGS: A Quick Overview](https://gameanalytics.com/blog/economic-research-mmorpgs-quick-overview.html)

Anderson notes that online games are not so simple so can’t be described as a simple economic loop. Online games tend to allow for player-to-player trading such that the buying and selling prices of items can fluctuate over time. For an offline game the game economy is a closed system and the game can follow a simple economic loop, while in an online game the economy is an open system and hence won’t be just a simple loop. That said, there can still be cycle mechanisms within an MMO economy, but prices will not follow a simple formula.

The “Control Systems'' page of Wikipedia notes that an open system does not have any feedback loops to control the input; however, economies (real or virtual) do have feedback loops where the output can affect the input. So the usage of “open system” in this book is closer to that of [thermodynamics](https://en.wikipedia.org/wiki/Thermodynamic_system#Open_system):

> “In an open system, there is an exchange of energy and matter between the system and the surroundings. The presence of reactants in an open beaker is an example of an open system.
It is named closed, if borders are impenetrable for substance, but allow transit of energy in the form of heat, and isolated, if there is no exchange of heat and substances.”

For an offline game, the “mass” of items can always be easily counted and there known. For an online game the exact “mass” of items can’t be so easily determined as players may log out and then not login again for a long time (sometimes never).

<p align="center">
  <img src="/images/economics/OpenSystemRepresentation.png">
</p>


Figure 1: Open systems have input and output flows, representing exchanges of matter, energy or information with their surroundings. Source: [Complex system (Wikipedia)](https://en.wikipedia.org/wiki/Complex_system#/media/File:OpenSystemRepresentation.svg)
 
 
### Economic modelling
The open-ness of online games means that modelling their economy is difficult, much like with a real economy, which is summarised on the [Economic model article found on Wikipedia](https://en.wikipedia.org/wiki/Economic_model#Problems_with_economic_models):

> “Most economic models rest on a number of assumptions that are not entirely realistic. For example, agents are often assumed to have perfect information, and markets are often assumed to clear without friction. Or, the model may omit issues that are important to the question being considered, such as externalities. Any analysis of the results of an economic model must therefore consider the extent to which these results may be compromised by inaccuracies in these assumptions, and a large literature has grown up discussing problems with economic models, or at least asserting that their results are unreliable.”

Despite the difficulty in understanding market dynamics, it might be possible to gain a basic understanding via simple models. Ray Dalio describes economies as being like a simple machine ([How The Economic Machine Works by Ray Dalio - YouTube](https://www.youtube.com/watch?v=PHe0bXAIuk0)). He believes the economy is simpler than first appears.

The crux of his model is people transacting with each other, repeatedly. People transact with each other based upon human desires, and it is due to these desires that we see three main trends that dictate how an economy evolves:

1. Productivity Growth
1. Short-term debt cycle
1. Long term debt cycle

The model will not describe exact price changes, but rather Dalio outlines that prices will rise or fall based upon the supply and demand of an item.
Hitherto, we haven’t seen games with debt so this is one major divergence between a real economy and a game economy. Perhaps with blockchain technology, we will see a cross-over between DeFi and gaming such that debt-like instruments will appear in the future.
However, Dalio does point out that you can modify his model to remove debt (aka credit) and have an economy based purely on productivity, which is perhaps closed to the economy of an online game. The more activities that players in, the larger the in-game economy. Typically, online games feature an ever increasing amount of currency and resources (inflation).
 
### Comparing real economies to online game economies
The aforementioned [piece by Anderson](https://gameanalytics.com/blog/economic-research-mmorpgs-quick-overview.htm) references the work of [Castranova et al](https://journals.sagepub.com/doi/abs/10.1177/1461444809105346) ([PDF](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.193.6326&rep=rep1&type=pdf)) who calculated the size of an online game economy using dollars as a “measuring stick”. He was able to calculate a real-world value for a game economy. The author summarises the work as follows:

>” This article proposes an empirical test of whether aggregate economic behavior maps from the real to the virtual. Transaction data from a large commercial virtual world — the first such data set provided to outside researchers — is used to calculate metrics for production, consumption and money supply based on real-world definitions. Movements in these metrics over time were examined for consistency with common theories of macroeconomic change. The results indicated that virtual economic behavior follows real-world patterns. Moreover, a natural experiment occurred, in that a new version of the virtual world with the same rules came online during the study. “

This publication predates Dalio’s video, however the conclusions taken in corroboration with Dalio’s economy model indicate a path forward for game developers to begin to design their economy. Dalio provides a model for a real economy and Castranova points out that a game economy behaves like a real economy.
 
#### Characteristics
In addition to noting that an online economy is like a real economy, it is worth considering how to characterise an economy with particular relation to a game economy.

Wikipedia’s article on virtual economies outlines five main characteristics that describe a virtual economy. This information originally came from [Fairfield (PDF)](https://web.archive.org/web/20110812211944/http://www.bu.edu/law/central/jd/organizations/journals/bulr/volume85n4/Fairfield.pdf):

* **Rivalry**: Possession of a resource is limited to one person or a small number of persons within the virtual world's game mechanics.
* **Persistence**: Virtual resources persist across user sessions. In some cases, the resource exists for public view even when its owner is not logged into the virtual world.
* **Interconnectivity**: Resources may affect or be affected by other people and other objects. The value of a resource varies according to a person's ability to use it for creating or experiencing some effect.
* **Secondary markets**: Virtual resources may be created, traded, bought, and sold. Real-world assets (typically money) may be at stake.
* **Value added by users**: Users may enhance the value of virtual resources by customizing and improving upon the resource.

“The existence of these conditions create an economic system with properties similar to those seen in contemporary economies. Therefore, economic theory can often be used to study these virtual worlds.” - [Virtual Economy (Wikipedia)](https://en.wikipedia.org/wiki/Virtual_economy#Overview)

These characteristics should also be true for a decentralised game economy. Although there may be divergence in behaviours as it will be easier for players to trade their assets for real money and that players can have a stronger notion of ownership. 

Fairfield notes that virtual assets present in contemporary online games have characteristics like real property, not all jurisdictions yet honour virtual assets with real world property rights. With blockchain technology, the ownership of the assets may not change in a legal sense (de jure), but without an owner's private key it should not be possible to move an asset meaning that there is some sort of ownership right in practise (de facto).
 
### Sources and sinks: asset creation and destruction
The sources and sinks in an economy are the mechanisms by which items are created and destroyed. They dictate the supply of assets and game currency. Arguably this is the most important part of an online game as it controls the ease with which to get items. It can also influence the demand if the mechanisms are designed in such a way as to encourage players to return to an item’s source and harvest the resources repeatedly.

A bigger factor for determining the demand of an item is the utility of an item. An additional factor for demand is the “rivalry” factor where ownership of an item provides social signalling ability that conveys power or wealth. Ultimately, what drives demand is human desires as described by Dalio in his economic model.

The work of [Castranova et al](https://journals.sagepub.com/doi/abs/10.1177/1461444809105346) drew on the [Quantitative Theory of Money (QTM)](https://en.wikipedia.org/wiki/Quantity_theory_of_money) to posit two hypothesis that can tested for game economies:

* if the amount of money goes up, all else being equal, the price level should go up.
* if the amount of traded goods goes up, all else being equal, the price level should go down.

The consequence of this holding true, as measured by Castranova, is that the rates of item creation and destruction can have an affect on its price. This should not be a surprise as they are concise statements about supply and demand.

More sources, or greater ease of resource extraction, means a greater supply of assets. While more sinks, or a greater rate of resource destruction, will decrease the supply of assets.

This is inline with Dalio’s description of the economy as a machine. Castranova points out that game economies are not exactly like real economies, due to certain differences such as taxation. However, the QTM approach was his starting point for determining if a game economy mimics a real economy, such that common economic metrics can be re-used to measure game economies. His conclusion suggests that it is possible.
 
#### Inflation
Inflation should strictly be about the increasing supply of assets or currency, although it is commonly substituted for the phenomena of rising prices that result as consequence of an increased supply of currency. 

Inflation is a problem for online games where the supply of in-game currency typically increases monotonically. An ever increasing supply of currency has historically led to higher asset prices (dominated in the game’s native currency). The problem of inflation in online games is so widely seen that it has its own moniker: [mudflation](https://en.bitcoinwiki.org/wiki/Mudflation).

A consequence of “mudflation” is that players who play for the longest time tend to have the greater bank balances and hence have greater ability to stay ahead in online games. Consequently newer players are at a disadvantage when participating in the game and could perhaps be a driver for real-world trading of game currency.

If currency is slow to be removed, then rising prices may be counteracted if the supply of resources increases at a rate comparable to that of money inflation (refer back to Castranova’s hypothesis). Another possibility for reducing an inflating supply of in-game currency is the introduction of a premium currency which is mentioned in a later section.

Game designer [Ralph Koster](https://www.raphkoster.com/2007/01/17/flation/) described various methods for dealing with “mudflation” in a blog post on his personal website. The following list is a brief summary of the key points:

* Item decay, item deletion
* State / Character purges
* Orthogonal advancement paths
* Restrictions on trade (soulbinding)
* Shift attention from power gains to cosmetic gains

Item deletion can come via a natural gameplay mechanism, which can include transformation. Items may be transformed from one type of item to another as seen in crafting mechanisms. A single crafted item may require multiple raw resources.

The last point on advancement paths is about introducing better items that replace previous items as the most useful or most powerful. This is only a partial fix, but is likely more acceptable to a player base than simply deleting the game state and starting again. Koster is reluctant to continuously tweak economic parameters to drain inflation as he believes it has a “high cost” to players.

Soulbound items are those which are eventually bound to one account. The items may not be tradeable or are potentially tradeable until worn (i.e. to benefit from the item’s utility).

Extra Credits, a YouTube channel, suggest that the [introduction of a “reserve currency”](https://www.youtube.com/watch?v=sumZLwFXJqE) helps to reduce inflation by giving a floor to the value of the in-game currency.
 
#### Duplication
Item duplication is a severe form of inflation that results from players finding an exploit in the game’s software. Upon finding an appropriate exploit, players may create multiple copies of an item or currency. This naively appears to be an unsolved problem for modern MMOs (example from [OS RuneScape in 2019](https://www.youtube.com/watch?v=IBabr-3d2Ag)) despites decades of seeing this problem occur again and again. As from the above statements, duplication means an increase in the supply of an item and a reduction in the price of those items.

Blockchain technology should solve the duplication problem. This is something we immediately see as true by design (confer with Bitcoin solving the double spend and decentralised money creation problems). However, the supply of native coins (or tokens) is something that can be tuned to be inflationary by design, in addition the in-game currency may be independent of the native chain token. Consequently, blockchain technology does not fix inflation as it is a game design issue.
 
#### Multiple Currencies
Having multiple in-game currencies will ultimately affect the total supply of money and hence affect the prices of assets. This is pertinent to the problem of containing inflation. 

When players are forced to use only one currency, they have no choice but to increase the supply of in-game currency in order to purchase new items. If there is an option to purchase items in a different currency it places less demand on the in-game currency. Players have alternate choices so there is less reason to harvest in-game gold.

The ease of exchange from one currency to another is an indication of a particular currency's liquidity. Where inefficiencies exist, one currency may be more desirable than another such that item prices denominated in that currency may be higher.
 
#### Rares
While utility is a huge factor in determining the demand for an item, it is not the only factor. The social signalling of owning particular items is another large factor in determining the demand for an item. There can be a correlation between the supply, or rarity, of an item and it’s demand. It is common across many online games that rare items are desirable. 

Sometimes it seems that the items are desirable solely because they are rare. However, caution should be offered here as implied rarity alone is not enough to create demand. Two items which are similar in almost all respects except perhaps one aspect may appear as two separate rare items, but the market may not have enough demand to ensure that both items are priced equivalently.

Otherwise stated: too many rare items can lead is essentially inflation via another guise. The temptation for developers to “print” rare items could be seen as an easy way to please the population base, or potentially as a source of revenue should the developer sell the rare items for real-world money. However, as stated, adding rares faster than demand can absorb those rares (not enough money chasing those items) will cause a failure in those assets being valuable.

This claim is backed up by the works of Dalio and Castronova mentioned previously: there will only ever be a finite number of dollars chasing any given asset. This implies that there is a maximum rate at which rare items should be added to a game such that we can have an expectation of their price rising.

In the current blockchain gaming space more emphasis is put on rarity than on utility. Many blockchain games are simple in design so it is difficult to instill utility in a particular gaming asset. An example is CryptoKitties. There is an ever-increasing supply of unique cats, arguably they can all be unique and hence rare, but there is a lack of demand for the recent cats. Part of this is due to the lack of utility but also an ever increasing supply of cats without enough dollars chasing each cat on aggregate.

It is erroneous to overweight item rarity for building a game economy. However, well designed game mechanics will be complemented by the addition of rare items that make the game, as a totality, attractive to an increasing player base.
 
### Trade automation: vendors and auction houses
The flow of goods (trade) within a game is almost as important as the characteristics of the sources and sinks of the game’s assets.

For game designers, there is a balance to strike between realism, ease-of-transacting, and market stability. As games are supposed to be fun, trade mechanisms need to account for the fact that not all players will be able to trawl the game world finding the best deals. Imposing trading restrictions to mimic the real world may eliminate the joy or playing.

Players who are time-rich will gain an advantage in games that offer limited trade automation, while players who are cash-rich but time-poor will gain an advantage in games that offer maximal automation of trade.

The methods of trade offered will dictate the ease and speed at which trade can happen. In turn this affects liquidity and price discovery. While most online games offer player-to-player trading whenever the players’ characters meet in game, not all online games offer automated mechanisms.

Automation includes making global transactions easier as well as providing Non-Player Character (NPC) vendors that allow players to buy and sell assets without interacting with other players.

There are arguments both ways for including automation or not and it can take numerous forms, such as:

* **NPC vendors** who buy and sell items to and from any player. Typically, such vendors are specific to an in-game location and sell a small subset of all possible items. Also, items sold by the player to the vendor may not be made for sale to other players. NPC vendors are also a source and sink of assets and currency too.
* **Player owned vendors** who may sell whatever a player lists. In some games, the vendor may be allowed to make purchases. This is not a source or sink assets, but just a means of transacting one asset for currency.
* **Auction houses** allow players to list items that they wish to sell to other players. Auction houses act as a central point of clearing. Some games allow players to set their own prices (e.g. [SWTOR](https://swtor.fandom.com/wiki/Galactic_Trade_Network)), while others have an in-built pricing mechanism that automatically sets the price for the seller (e.g. [Runescape](https://runescape.wiki/w/Grand_Exchange)). The delivery of items could be instantaneous to an auction house (SWTOR, Runescape), or may require the player to visit another distant location (e.g. [SWG](https://swg.fandom.com/wiki/Bazaar_Terminal)).
* **Contracts** exist in some online games (e.g. [EVE Online](https://support.eveonline.com/hc/en-us/articles/203218982-Courier-Contracts)) to facilitate the delivery of items around the map in a way that encourages player participation to move the items, but also to provide some guarantees to prevent theft.
All of these aspects can be part of a decentralised game too, although over and above this, decentralised games allow for items to be traded outside of the game itself. The latter may include trades for real money. It is therefore possible that gaming items can be traded on a market that exists entirely external to the game mechanics (for example, [OpenSea](http://opensea.io/)).
 
### Currency Types
For traditional online games, there are two main types of currency plus a couple of other possibilities which are proxies for currencies such as “time” or “assets”.

As mentioned previously, if conversion from one currency to another is difficult, players may pay a premium when buying items in the currency that is easier to obtain. The reason is that there is a trade-off between an extra amount of time required to perform the conversion versus buying the item at a higher price.
 
#### Standard
All online games have at least one standard in-game currency such as gold pieces ([RuneScape](https://en.wikipedia.org/wiki/RuneScape#Player_interaction), [World of Warcraft](https://worldofwarcraft.fandom.com/et/wiki/Currency)) or Interstellar Kredits (ISK) ([EVE Online](https://en.wikipedia.org/wiki/Eve_Online#Economy)). Some games also have multiple types or classes of standard currency, such as gold, silver, and bronze ([World of Warcraft](https://worldofwarcraft.fandom.com/et/wiki/Currency)).

Most traditional publishers do not allow the conversion of standard currency into real-world currency. Although most blockchain and decentralised games already allow this.
 
#### Premium
In an effort to combat real-world trading, as well as to boost revenue, game publishers may sell a premium currency which can be purchased using real-money and then used to subsequently purchase items in-game. Those in-game items can then be sold for standard currency. However, the reverse path tends to be forbidden.

RuneScape introduced the idea of “Bonds” which are its form of premium currency while [EVE Online has PLEX](https://secure.eveonline.com/plex). Both premium currencies can also be used to purchase subscription time.

Extra Credits, a YouTube channel, describes premium currencies as being like the reserve currency of a country. They state that the [introduction of a “reserve currency”](https://www.youtube.com/watch?v=sumZLwFXJqE) helps to reduce inflation by giving a floor to the value of the in-game currency.

In this video, they mention premium currency (although refer to it as reserve currency). Premium currency being something like PLEX where you use real money to buy a currency which can only be spent on game items. Rarely are you allowed to sell the premium currency again for real money, so it is pretty much a one-way transfer. In many games you can't buy premium currency with in-game currency, although not always the case.

Extra Credits cite this as a way to reduce rising prices. The reasoning is that prices won't rise when priced in in-game currency as the conversion rate to premium currency puts a floor under the value of the items in real-money terms. However, this does not necessarily have to be true. The inclusion of a premium currency does not put a hard cap on the amount of in-game currency being generated, which could result in market inefficiencies.

Market participants are often willing to pay a premium when using a more liquid (more useful) currency, or consequently get a discount when using an illiquid currency. This reduces the “hardness” of the price floor.

Following the line of reasoning from Dalio and Castranova, it could be possible that a premium currency could help reduce price inflation as there is lesser demand placed upon the standard in-game currency. When players are forced to use only one currency, they have no choice but to increase the supply of in-game currency in order to purchase new items.

If there is an option to purchase items in a different currency it places less demand on the in-game currency. Players have alternate choices so there is less reason to harvest in-game gold.

Premium currencies will not be possible in a decentralised game, as there is no decentralised way for developers to accept payment in return for giving players a reward. However, other options exist as will be explored in the later sections.
 
#### Assets
A subtle point is that some assets can be liquid enough to be considered a currency and depending on the game design, they may be preferred over the standard currency when trading player-to-player.

Particularly, when in-game currency is devalued so strongly that it becomes easier for players to trade assets than currency.
 
#### Time
Providing an in-game service can be possible in current online games, although any activity that involves having another person logging into another person’s account (e.g. to gain experience) is against a game’s EULA.

Decentralised games are more receptive to allowing real-world trading and hence enable a phenomenon known as “Play2Earn”.
 
### Real-World Trading
RWT, is also known as Real-Money Trading (RMT). For almost all MMOs, trading game assets or currency for real money is against the rules. While this has happened in the [past](https://www.wired.com/2003/01/gaming-2/), most traditional publishers do not allow the conversion of standard currency into real-world currency as will be mentioned later. A notable exception to this is [Second Life](http://www.secondlife.com/).

This is due to two main factors:

* Preventing play-to-win: and
* Reducing credit card fraud.

The former is seen as undesirable by many players, while the latter can lead to problems for the game publisher.

Blockchain games (including those which are fully decentralised) do tend to push the notion of “true ownership”, such that assets can be traded for real-money. Opening up trade will affect the dynamics of the in-game market.
 
#### End-User License Agreements
Some of the earliest MMOs saw game assets and currency being traded for real world currency, such as **Ultima Online** and **EverQuest**. As mentioned, it was permitted in the [past](https://www.wired.com/2003/01/gaming-2/), but it is not permitted now under the current EULA for each respective game ([UO](https://tos.ea.com/legalapp/WEBTERMS/US/en/PC/#section3), [EQ](https://www.daybreakgames.com/terms-of-service#section13)). Moreover, the EULAs make it clear that the game producers technically own the content.

Likewise, this is also true for **EVE Online** and **RuneScape**. Despite the illegality of real-world trading according EULAs, there are [black markets for many online games](https://en.m.wikipedia.org/wiki/Virtual_economy#Black_market). One example is the currency of Old School Runescape being used as a real-world currency in [US prisons](https://www.youtube.com/watch?v=lWZHLJ7TIgI).

A notable exception to these strict rules is Second Life ([EULA](https://www.tilia-inc.com/legal/tos/#virtual-tokens)).
 
### Crowdfunded games
The concept of crowdfunding a game is to ask the future players to pay for the game in advance of the game being built. In exchange for helping to build the game, the backers of the campaign will be given rewards. Typically, these rewards are larger than what are granted to new players who purchase the game at release.

Crowdfunding allows game developers to be independent from the big publishers and retain their own vision for the project. The most common place for crowdfunding games has been via [Kickstarter](https://www.kickstarter.com/), and is somewhat similar to ICO funding where the potential future users help to fund the project. It is expected that crowdfunding will be the most typical approach pursued by decentralised game development teams.

The games that have raised the [largest amount of funding](https://en.wikipedia.org/wiki/List_of_video_game_crowdfunding_projects) (Shroud of the Avatar and Star Citizen) both continued to raise funds on their website after the Kickstarter campaign ended.

A big concern is that both games sold a large number of items to raise funds for development. This means that from day zero of the game’s life a lot of assets will already exist, some of these assets will be high-end valuable assets which are typically not available until the latter stages of character progression. This will likely have a non-negligible effect on the games’ economies.

Crowdfunding will be the most popular method of raising funds for a decentralised game, this means that there could also be a large supply of items and a potential imbalance in the respective economics.

While the developers of centralised games can continue to inject new items into their games, injecting new items or currency into a decentralised game after it has launched is a challenge for decentralised games. As mentioned, developers should not occupy such a privilege role if the game is to be properly decentralised.

#### Examples
The following two games are the two most successful non-blockchain games that pursued crowdfunding.

##### Star Citizen

Star Citizen is the game with the biggest amount of funds raised via crowdfunding. The total amount of funding now exceeds $275 million, of which [$6.2 million came from their Kickstarter campaign](https://en.wikipedia.org/wiki/Star_Citizen#Crowdsourcing). The rest was mainly raised via their website.

The majority of funding came from players who have purchased game assets in advance of the game being launched. This will likely have an impact upon the economy as there is a large supply of items at the beginning of the game. At the time of writing the game has not launched.

##### Shroud of the Avatar

[Shroud of the Avatar](https://www.shroudoftheavatar.com/) is listed as the game with the second highest amount of crowdfunding. During their Kickstarter campaign, the development team implied that pledge levels sold would be limited in number, which naturally inspired players to pledge at a higher level than might otherwise happen. However, after the campaign ended the pledge levels continued to be sold on the game’s website.

This calls into question the notion of rarity implied during the Kickstarter campaign. While continuing to sell pledges on the game’s website allows for additional funding to develop the game, it did not honour the idea of being time-limited. Eventually, the Kickstarter pledges were removed and replaced with packages that promise less items once purchased.

Similarly, the team made sold rares as seasonal items that recurred each year. While slight differences exist from year to year, the notion of rarity can be questioned when new rare items are continually added to the game.

One promise made during the Kickstarter campaign was to allow for real-world trading and that was certainly possible and even condoned while the game was still in development. This took away some of the risk of backing the game as unhappy backers could sell their pledges. Some even made a profit doing so. After the game launched, the development team had to prohibit real-world trading.

As development continued, the player base gradually grew less happy which means that real-world liquidity has dried up despite real-world trading being possible. This will be a challenge for decentralised game developers too: simply allowing real-world trading, or promising rares, does not guarantee that there will be real-world demand.

 
## Decentralised Game Economics
The principles that shape traditional game economies will also hold true in decentralised game economies. The concerns around sources, sinks, and inflation will still hold true in a decentralised game. Human behaviour is still driven by desire, this does not change because a blockchain is attached.

That said, there are additional nuances to consider. One of the most obvious differences is the addition of a blockchain, which necessitates considerations of the economics to secure the chain. Typically, this is about providing tokens to the agents that provide **security for the chain**. A related point is that all actions in the game are recorded on-chain and so a fee must be charged to prevent spam.

Adding a blockchain to a game can provide benefits as we hope to argue throughout this book, but in the area of economics it provides an amount of **transparency** (as we see with Bitcoin and Ethereum) that can be used to hold the developers **accountable**. The **provenance** of all items will be provable which should eliminate duplication, and hence provide provable **rarity**.

Blockchain technology will allow for real-world trading and also provide a greater trade **automation** such that assets can be outside of the game mechanics. The greater ease with which to conduct **RWT** will likely have an impact on the pricing seen within the game. It may increase the real value of items, by allowing for greater demand on each item, while keeping the supply of in-game currency low.
As discussed in the [chapter on challenges](05_challenges_of_building_a_decentralised_game.md), the autonomous nature of blockchains and the difficulty in coordinating upgrades of the software presents new challenges in updating decentralised game economies. Upgrading blockchains is not as straight-forward as upgrading traditional software. There needs to be a more explicit level of social consensus for the upgrade to be accepted by the community.

A lot of the ideas expressed in the remaining part of this chapter will be theoretical possibilities which may not have been fully tested. The ideas will still be within the realm of what’s possible within the near future given what’s possible with blockchain technology today. Before digging into the theoretical possibilities of what could be done, we will take a look at what we see now in the decentralised gaming space.

This section will re-examine key factors of a game economy and how they will change with the benefits offered by blockchain technology.
 
### Current Decentralised Games
Before jumping into how the previously introduced economic ideas change with respect to blockchain games, it will be pertinent to briefly summarise the economics of current decentralised games.
 
#### Xaya
As [Xaya](http://xaya.io/) are one of the few teams building in the space of decentralised gaming it is difficult to provide many examples of what teams are currently doing. The team are the builders and maintainers of the Xaya blockchain which is a Proof-of-Work (PoW) chain that allows multiple games to run on top of it.

The team raised an initial amount of funding via an ICO of their chain’s native token (CHI). These native tokens are also provided as a reward to miners of their chain. The rate of issuance and the maximum possible number of coins ever is known in advance as we see with Bitcoin. The limited scarcity of tokens is the economic principle upon which Bitcoin built upon. If the tokens are useful then they have real value, this in turn provides an incentive for miners to continue to mine and secure the chain.

The Xaya team is currently building [Taurion](https://taurion.io/) which is an MMO-scale RTS game. The in-game currency "Cubits" (previously vCHI) is first obtained by burning the chain's native token CHI (earned via mining). Burning removes CHI from the total supply. Once a player has obtained Cubits, they can freely exchange them with other players which includes trading back to CHI. In addition to Cubits, the in-game resources can also be freely exchanged with each other and have a inflationary supply. Although the game loop encourages harvested resources to be crafted which transforms them into a fewer number of higher value items.

A separate team is building the [Soccer Manager Elite](https://soccermanagerelite.com/), an MMO-scale football management game, which also runs on top of the Xaya blockchain however their in-game currency is separate from the native chain token. 
 
#### Planetarium
The [Planetarium](http://planetarium.io/) have raised private investment for their game. They are building both a chain and a game; their current thinking is to have one game per chain. As the chain is also PoW this means that miners who provide the economic security of the chain will be rewarded with the native chain token.

It remains to be seen if the tokens earned via mining can be spent in game or if that will be separate from the in-game currency seen in the Alpha release of their first game [Nine Chronicles](https://nine-chronicles.com/).
 
#### Ethernal
At the time of writing, Ethernal is also in at a alpha stage. It is built using Solidity and is designed to run on an Ethereum sidechain. The developers presupposed that the chain is already secure and fit for the purpose of hosting their game.

The native token of the underlying sidechain is an integral part of the game mechanics: players must expend the native token in order to perform action (as with Xaya). Although the developers abstracted this aspect of the mechanics by labelling the currency as ‘food’ which depletes as the player moves around the map.

Players can collect a different type of currency in the game that covers the cost of levelling up (a fee is paid to formally move from one combat level to the next). Later in development, it may be that this currency can also be used for player-to-player trading.
 
### Economics of chain security
As the addition of a blockchain is a new feature for decentralised, this is the first topic to tackle in this major sub-section on decentralised game economics. Some developers may wish to build their own chain, which in turn necessitates thinking about the economics of chain security while other developers will assume that a secure chain already exists and hence be concerned only with the in-game economics.

Should developers wish to build upon another platform then they can, to an extent, assume that chain security is independent of their game. For example, if a developer is building upon Xaya, Ethereum, an Ethereum side chain such as Matic, or a Polkadot parachain, it may be fine to assume that security is already provided by the existing blockchain.

The following descriptions illustrate the current design thinking around the security of  contemporary blockchains.
 
#### Bitcoin
The most well known blockchain, although not one that hosts any games, it does have a major role in illustrating the economics of chain security. The supply rate of [bitcoin](https://bitcoin.org/en/) follows a known trajectory where the rate will decrease over time and implicitly meaning there is a maximum supply amount (21 million bitcoins, as shown in the Bitcoin whitepaper ([PDF](https://bitcoin.org/bitcoin.pdf))).

The fixed total supply was a design choice from the beginning and stands in contradistinction to leading fiat currencies that do not have a maximum total supply and can be inflated as determined by the respective government. The limited supply somewhat expects the price of bitcoin to rise relative fiat currencies in order to subside the cost of the miners providing security to the network.

Governance is informal and roughly follows the consensus of the community. Although it is a hotly debated topic of how the governance process actually works.
 
#### Ethereum
The [supply rate of ether](https://docs.ethhub.io/ethereum-basics/monetary-policy/) is not fixed in the same way that bitcoin is, so the rate is not entirely known ahead-of-time (only in the short to intermediate term). The supply rate is fixed for some amount of time until changed via [Ethereum’s governance process](https://docs.ethhub.io/ethereum-basics/governance/).

A supply rate is picked that the community believes will best serve the purposes of rewarding the agents who secure the chain. At the time of writing, Ethereum is still a proof-of-work chain where rewards are paid out to miners, while in the future it will transition to being a proof-of-stake chain.

Like Bitcoin, Ethereum governance follows what can be described as “rough consensus”.
 
#### Grin
Unlike the previous two mentioned projects, the Grin project is taking a different approach with its [supply rate](https://github.com/mimblewimble/grin/blob/master/doc/grin4bitcoiners.md#emission-rate). Grin has a fixed rate of supply which is linear in time, but there is no maximum number of tokens. However, the project has not seen enough demand to keep the price either rising or constant. Consequently, the price has been mostly downwards since launch since supply is always increasing. This does not bode well for the long-term security of the chain.
 
#### Polkadot
Polkadot is a sharded blockchain platform where each of the shards can be different. The project had a phased launch over the summer of 2020. It represents a new generation of blockchain projects that offer the ability to host and connect different blockchains together. The shards of Polkadot can benefit from a [shared pool of validators](https://wiki.polkadot.network/docs/en/learn-security), meaning that the security proposition of launching a new chain is easier 
 
The exact rate of inflation is not set in stone for all time, but rather it can be updated via an [on-chain governance mechanism](https://wiki.polkadot.network/docs/en/learn-governance). However, each shard can issue its own token with its own rate of issuance. One such shard could even be dedicated to gaming.
 
 
 
### Transaction fees to prevent spam
One obvious difference between blockchain games and non-blockchain games is that transaction fees must be paid in order to either trade (centralised NFT games) or record an action on-chain (fully decentralised blockchain games). In both cases, there is an interaction with a blockchain which necessitates the payment of a fee. Almost all blockchains charge a fee as a way to protect against spam (as described in the [Xaya documentation](https://github.com/xaya/xaya/blob/master/doc/xaya/games.md#chi-transactions-in-games-)).

These fees are necessary, but they do create a barrier of resistance that makes the freemium (free-to-play) model difficult to replicate with blockchain technology. It also means that players don’t pay a fee for a specific amount of time, but rather for a number of actions. The former is what we see with typical MMO subscriptions. If the chain fees are dynamic then players do not know how many actions they can perform for a given amount of tokens.

These fees are paid using the native token of the underlying chain and may be given as a reward to the nodes securing the network, but it is also possible that some portion of that fee goes to the developers as means of funding game development. As seen with Xaya, an alternative is to burn the native chain tokens instead of paying the developers. The latter affects the total supply of tokens and could have an effect on the token’s price or the price of game items.

There are some interesting possibilities where the transaction fee can be paid in a different token from the native chain token. Players may be able to purchase a separate token which grants them an amount of actions. The Planetarium team do this by including "Energy Potions" in their game Nine Chronicles. These tokens grant players the ability to perform an action and are different from the chain's native token (Nine Chronicles Gold).

In order to mimic a typical MMO subscription, a game could force players to buy new action points every month by having a decay function burn the unused action points at the end of each month.

It could be possible to replicate a freemium experience by modifying the fees depending on a player's location, such that some areas could be free-to-play, while other regions could be made progressively more expensive where the loot also gets better. Additional anti-spam measures would be required in the free-to-play areas and ultimately the costs are subsidised by the premium areas.


### Sources and sinks: asset creation and destruction
Just as with the traditional online games, the sinks and sources of item creation and destruction are just as important for a decentralised game. The economics of supply and demand still hold true.

Given the public nature of blockchain data it ensures that anyone can check the data that exists on chain. Naturally, this requires having either the technical ability to query the data or to have a block explorer that sufficiently provides the data. New chains typically lack a block explorer, but it is one of the most beneficial services that can be provided to a community. Ideally, the block explorer should be open source too.

This means that a decentralised game can have a fully transparent economy. All items and currencies can be tracked across all players. This should guarantee the impossibility of duplication and ensuring provenance of all items (including rares). The level of transparency offered allows players to hold developers accountable in a way that wasn’t possible before with centralised games.

It should be noted that while public data offers transparency it is a hindrance to privacy. Not all players will want their game account’s bank balance to be known to other players.


#### Inflation
Bitcoin is a technological solution to the social desire of having a form of money that is not susceptible to the inflation that we see in either the real economy. This anti-inflation design would be applicable to the token that secures the chain, but may not be wholly desirable for an online game.

Inflation is a problem for online games whenever prices rise too quickly; however, it may not be a huge problem whenever the rate of increase is sufficiently low. For example, pLayers should not be demotivated that prices rise faster than the majority can afford, or when the main currency becomes worthless that an asset is used in place of an in-game currency.

While blockchain may offer transparency for the economy it does not guarantee that inflation will be kept in check. Duplication should be prevented, but ultimately inflation is a concern for game design and how easy it is to create new items. All of the previous concerns around the lifecycle of in-game resources will still apply to a decentralised game.

Given the ease of which RWT is enabled within decentralised games, then it could be the case that demand for in-game currency is reduced and hence the rate of supply is similarly reduced. This is discussed further in the trade automation section.


#### Duplication
One of the most well-known benefits of blockchain technology is the ability to prove the rarity and provenance of an item. For simple blockchain games, as seen on Ethereum, NFTs are used to track game assets. Each NFT has an unique ID, such that all assets can also be identified uniquely. The unique identification of assets should prevent duplication which has plagued contemporary MMOs and often resulted in a huge amount of inflation of items and hence drive their price down.

#### Rares
As mentioned, NFTs enforce all game assets to be tracked uniquely. This in combination with the transparency offered by blockchain technology allows all assets to have a known and provable rarity that can be checked by all players. 

Naturally, this presupposes that the game is fully decentralised. If a game is centralised, then it is only possible to check the provenance of the tokens not ultimately of the assets.

While game assets should be in a one-to-one relationship, it wouldn’t be possible to prove this with a centralised game when there is no access to the game developer’s server data. This is one edge that decentralised games have over blockchain games that use a hybrid architecture of on-chain tokens but centralised assets: decentralised games offer transparency such that all game assets have a known supply and provenance. If NFTs are used, which is optional, then there is a one-to-one relation between each NFT and each asset.


### Trade automation and real-world trading
Trade automation in traditional online games could be summarised as making the gameplay experience more frictionless and thus easier for the players to buy and sell what they need without scouring the map looking in places they are unfamiliar with. Providing a global reference point for pricing (although not necessarily singular pricing) allows players to know that they have found the current best deal which goes some way to levelling the playing field between new and veteran players.

All of the mechanisms provided are done inside the game. All of these mechanisms can be replicated in decentralised games, although given that blockchains tend to be public with publicly accessible API, it is possible for players to create their own software to perform trade automation. The outcome is that anyone can buy, sell, and auction their items outside of gameplay, but as the underlying blockchain will settle all trades then there is no reduction in security.

From an architecture point of view, game builders should be mindful to update the inventory from the data seen on-chain (which is the point of truth). The ordering of trades will matter in order to avoid duplication or other erroneous behaviour.

Arguably, out-of-game trading, should further reduce the friction of trade between players and enable greater price discovery. It will also enable trading items for multiple different cryptocurrencies, especially as we enter a new paradigm of cross-chain communication which is coming to life at the time of writing (2020).

Consequently, this may reduce the demand for in-game currency and hence reduce the rate at which new currency is minted. The hope is that prices in-game currency don’t so easily suffer from “mudflation” that we see in many modern MMOs. It may also increase the prices by allowing for greater demand on each item, while keeping the supply of in-game currency low.

We already see the signs of external trading sites appear for current blockchain games. For example, we see NFTs from multiple different games being traded on [OpenSea](http://opensea.io/)).

### Currency Types
As with traditional online games there is the option to create a decentralised game with multiple currencies. The simplest choice would be to have a single currency, the native token currency, however the economic properties of such a currency may not be well suited to all game types.

In this section we will review the different options that could be employed in a decentralised game.

In the emerging multichain future, it should be easy to trade one cryptocurrency for another. Moreover, a decentralised game could allow the player to trade assets for a variety of different tokens within the game, even tokens which are not native to the game. In short, there could be a decentralised exchange linked to the game.

As blockchain games, as a whole, are friendly towards the idea of RWT, there is a growing expectation that it could be possible to play a game to earn real money. Collected game items would be freely tradeable for other cryptocurrencies without fear of breaking the game EULA. This desire to allow RWT is being coined as “Play2Earn”.
 
#### Native chain token
The native token of the chain will be used to reward the agents of the network who provide chain security. For example, miners in a PoW chain or validators in a PoS chain. It is possible that this currency is also used as the in-game currency, however, the economics of chain security will likely override the value of that currency which would be derived from in-game mechanics.

Typically, native chain tokens are not inflationary but often have a known maximum supply. This affects the price of the currency, which many may see as good, however there has also been extreme volatility seen in the cryptocurrency space which may not be conducive to providing a good in-game currency. Therefore, it may be wiser to separate the in-game currency from the native token currency.

The two should be freely exchangeable as players desire.
 
#### In-game currency
This currency is likely inflationary in nature as we see in contemporary online games, but that is not necessarily a problem if this is the expectation from the beginning. The addition of RWT plus the other currencies, it is hoped that inflation can be kept under control in a better manner than we see with contemporary online games.

As seen with existing games, it is possible to have multiple types of in-game currency as we see with World of Warcraft. However, it is unlikely that there can ever be a premium currency. In a decentralised game, developers should not have the ability to grant additional power or provide favours to any player, which means it is not possible for a developer to accept payment and in return provide a reward to a player.

While premium currencies may help to reduce inflation in contemporary online games, there are other options available to decentralised game developers. Players can potentially trade their items for any cryptocurrency.
 
#### Stablecoin
The advent of stablecoins in blockchain has seen the rise of decentralised finance. People can also collateralise their cryptocurrencies and borrow against them. Such complex financial systems could also end up in decentralised games; however, at a simpler level it would also be beneficial to have an in-game currency that trades at a stable value to fiat.

Players would not have to hold their in-game wealth in the inflationary game currency, but could instead convert to a stablecoin. This offers protection against inflation without pushing them to hold the potentially volatile chain token.

### Crowdfunding
This is the most likely method of funding a decentralised game, as it has been arguably the most popular method for funding traditional indie games in recent years and many blockchain projects. It seems like a natural fit for open-source decentralised games. This section encourages crowdfunding, but cautions the developers to consider the consequences of over-promising on providing items to the player base.

Providing too many items during the crowdfunding phase will have a long-term effect on value of items in the game economy depending on the nature of items offered. Similarly, promising rare items during the crowdfunding phase is easy, especially when the game does not exist players depend on the developers to be honest honour the delivery of the items when the game is launched but also not to continue creating new items.

Examples of crowdfunded games were given in the previous crowdfunding section under Traditional Game Economics.
 
### Upgradability
The difficulty with which to upgrade a blockchain can be seen as a pain point for the technology. Ultimately, it comes down to a question of governance. There is an expectation of immutability with blockchain data such that upgrading the software is done cautiously.

This is relevant to economics as it is a statement about how easy or difficult it is to adjust the economic parameters or mechanisms within the game. As game developers can set the rarity of resources, they have godlike powers to set the pace of how quickly the economy evolves. Otherwise stated, developers have an ability to influence inflation within their games.

Adjusting the parameters or updating the software of the chain in such a way to make a new version incompatible with previous versions will require a fork and is an issue of governance.

That said, the upgradeability of a decentralised game can be seen as independent to that of the chain. It is possible to upgrade a game where most of the computation is off-chain without affecting the need to change the underlying node software.

Three possible paths:

* Auto-update the software, which is ultimately off-chain.
* Follow the governance methods in Bitcoin and Ethereum (rough consensus)
* Employ an on-chain governance mechanism where user votes are recorded on-chain and potentially enforceable.
 
## Summary of Factors
Enumerating every factor that contributes to the dynamics of a gaming economy is perhaps impossible, but here we identified the factors that should be the most important. Some factors apply to traditional games, while others apply only to decentralised games where there are also economic security considerations of the underlying chain.

Fundraising:

* Fundraising to build the chain (if not already built).
* Fundraising to build a game (could be separate from fundraising to build the chain).
* Fundraising to maintain the chain and games that run on top of the chain.
 
Economics of Chain Security:
* Token economics to maintain the security of the underlying blockchain, and their link to the in-game economy.
 
Economic Loop:
* Spawn rates of resources and in-game currency to ensure a healthy economy.
* Real-world trading and liquidity.
* Growth rate of players and the rate at which accounts go inactive.
* Updating game economics in an autonomous world
 
# References
 
## Traditionally Published Games
* [Virtual Economy (Wikipedia)](https://en.wikipedia.org/wiki/Virtual_economy)
* [Economic Research On MMORPGS: A Quick Overview - Anderson ](https://gameanalytics.com/blog/economic-research-mmorpgs-quick-overview.html)
* [Thermodynamics: Open System  (Wikipedia)](https://en.wikipedia.org/wiki/Thermodynamic_system#Open_system)
* [Complex system (Wikipedia)](https://en.wikipedia.org/wiki/Complex_system#/media/File:OpenSystemRepresentation.svg)
* [Economic model: Problems with economic models (Wikipedia)](https://en.wikipedia.org/wiki/Economic_model#Problems_with_economic_models)
* [How The Economic Machine Works - Ray Dalio (YouTube)](https://www.youtube.com/watch?v=PHe0bXAIuk0)


### Comparing real economies to online game economies
* [As real as real? Macroeconomic behavior in a large-scale virtual world - Edward Castranova et. al.](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.193.6326&rep=rep1&type=pdf) ([PDF](https://journals.sagepub.com/doi/abs/10.1177/1461444809105346))
* [Virtual Property - Joshua A. T. Fairfield (PDF)](https://web.archive.org/web/20110812211944/http://www.bu.edu/law/central/jd/organizations/journals/bulr/volume85n4/Fairfield.pdf)
 
 
 
#### Characteristics
* [Virtual Economy Characteristics (Wikipedia)](https://en.wikipedia.org/wiki/Virtual_economy#Overview)

### Sources and sinks: asset creation and destruction
* [Quantitative Theory of Money](https://en.wikipedia.org/wiki/Quantity_theory_of_money)
 
#### Inflation
* [Mudflation (Wikipedia)](https://en.bitcoinwiki.org/wiki/Mudflation
* [‘Flation - Ralph Koster](https://www.raphkoster.com/2007/01/17/flation/)
* [MMO Economies - Hyperinflation, Reserve Currencies & You! - Extra Credits (YouTube)](https://www.youtube.com/watch?v=sumZLwFXJqE)
 
#### Duplication
* [RuneScape Was Just Exploited. They Duped Trillions of Gold - SirPugger (YouTube)](https://www.youtube.com/watch?v=IBabr-3d2Ag)
 
### Trade automation: vendors and auction houses
* [SWTOR Galactic Trade Network](https://swtor.fandom.com/wiki/Galactic_Trade_Network)
* [Runescape Grand Exchange ](https://runescape.wiki/w/Grand_Exchange)
* [SWG Bazaar Terminal](https://swg.fandom.com/wiki/Bazaar_Terminal)
* [EVE Online](https://support.eveonline.com/hc/en-us/articles/203218982-Courier-Contract)
* [OpenSea](http://opensea.io/)
 


### Currency Types

#### Standard
* [RuneScape](https://en.wikipedia.org/wiki/RuneScape#Player_interaction)
* [World of Warcraft](https://worldofwarcraft.fandom.com/et/wiki/Currency)
* [EVE Online](https://en.wikipedia.org/wiki/Eve_Online#Economy)
 
#### Premium
* [EVE Online - PLEX](https://secure.eveonline.com/plex)
* [MMO Economies - Hyperinflation, Reserve Currencies & You! - Extra Credits (YouTube)](https://www.youtube.com/watch?v=sumZLwFXJqE)
 
### Real-World Trading
* [The Unreal Estate Boom - Wired](https://www.wired.com/2003/01/gaming-2/)
* [Second Life](http://www.secondlife.com/)
 
#### End-User License Agreements
* [The Unreal Estate Boom - Wired](https://www.wired.com/2003/01/gaming-2/)
* [Ultima Online EULA](https://tos.ea.com/legalapp/WEBTERMS/US/en/PC/#section3)
* [EverQuest EULA](https://www.daybreakgames.com/terms-of-service#section13)) 
* [Black markets in virtual economies (Wikipedia)](https://en.m.wikipedia.org/wiki/Virtual_economy#Black_market)
* [Second Life EULA](https://www.tilia-inc.com/legal/tos/#virtual-tokens)
 
### Crowdfunded games
* [Kickstarter](https://www.kickstarter.com/)
* [List of crowdfunded games (Wikipedia)](https://en.wikipedia.org/wiki/List_of_video_game_crowdfunding_projects)
* [Star Citizen](https://en.wikipedia.org/wiki/Star_Citizen#Crowdsourcing)
* [Shroud of the Avatar](https://www.shroudoftheavatar.com/)
 
## Decentralised Games
### Current Decentralised Game Economics
* [Xaya](http://xaya.io/) 
* [Taurion](https://taurion.io/)
* [Soccer Manager Elite](https://soccermanagerelite.com/)
* [Planetarium](http://planetarium.io/) 
* [Nine Chronicles](https://nine-chronicles.com/)
 
### Economics of chain security
#### Bitcoin
* [Bitcoin.org](https://bitcoin.org/en/)
* Bitcoin whitepaper ([PDF](https://bitcoin.org/bitcoin.pdf))
 
#### Ethereum
* [Supply rate of ether](https://docs.ethhub.io/ethereum-basics/monetary-policy/)
* [Ethereum’s governance process](https://docs.ethhub.io/ethereum-basics/governance/)
 
#### Grin
* [Grin Emission Rate](https://github.com/mimblewimble/grin/blob/master/doc/grin4bitcoiners.md#emission-rate)
 
#### Polkadot
* [Polkadot Security](https://wiki.polkadot.network/docs/en/learn-security)
* [Polkadot Governance](https://wiki.polkadot.network/docs/en/learn-governance)
 
### Transaction fees to prevent spam
* [Xaya - CHI Transactions in Games](https://github.com/xaya/xaya/blob/master/doc/xaya/games.md#chi-transactions-in-games-)
