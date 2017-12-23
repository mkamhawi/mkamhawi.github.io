---
layout: post
cover: 'assets/images/blockchain.jpg'
title: "What is Blockchain and how does Bitcoin work"
date:   2017-12-23 11:33:33
tags: tech computers blockchain bitcoin
subclass: 'post tag-tech tag-computers tag-blockchain tag-bitcoin'
categories: 'mkamhawi'
disqus: True
navigation: True
---

Blockchain is great technology, it promises to disturb and change a number of
industries that is not limited to the technology scene.

The most famous application for the blockchain is BitCoin. and if it can navigate
and escape the gambling craze happening right now, it can be the next big step in
the evolution of the economy and the financial industry. but cryptocurrencies are
not the only application for the blockchain technology, we are only scratching
the surface of what is possible.

What the blockchain achieves is that it liberates us from the need to keep a central
record for any type of valuable assets. blockchain is a distributed system, every
user in the system helps keep track of who owns what.

## understanding the blockchain: bitcoin as an example

Right now the financial system and the economy is built on the presence of central
banks responsible for printing banknotes, these banks must be trusted by the public
for those notes to have any value, and these banks are responsible for guaranteeing
a stable value for those notes.

In a network like bitcoin's, no central entity exist, nobody has the power/responsibility
of keeping record of transactions, instead, the transaction record (the ledger) is public,
it is shared across the network, people can download it and keep track of whats happening,
and even insert transactions in it. this seems a bit chaotic, but all this happens
according to rules defined in the software, the code on which the system runs.

#### History of the bitcoin

![bitcoin logo]({{ "/assets/images/bitcoin.png" | absolute_url }}){:width="250px" align="right"}

in 18 August 2008, the domain name [bitcoin.org](https://bitcoin.org){:target="_blank"}
was registered. In November that year, a link to a paper authored by *Satoshi Nakamoto*
titled “Bitcoin: A Peer-to-Peer Electronic Cash System” was posted to a cryptography
mailing list.

Nobody knows who is *Satoshi Nakamoto*, he implemented the bitcoin software as
open source code and released it in January 2009.

In January 2009, the bitcoin network came into existence after *Satoshi* mined
the first ever block on the chain, known as the genesis block, for a reward of
50 bitcoins.

![The Times Jan 3rd headline]({{ "/assets/images/times.png" | absolute_url }}){:width="250px" align="right"}
Embedded in the coinbase of this block was the following text:

>  “The Times 03/Jan/2009 Chancellor on brink of second bailout for banks.”


This was probably intended as proof that the block was created on or after January
3rd 2009, as well as a comment on the instability caused by fractional-reserve banking.
Additionally, it suggests that *Satoshi Nakamoto* may have lived in the United Kingdom.

Programmer *Hal Finney* downloaded the bitcoin software the day it was released,
and received 10 bitcoins from Nakamoto in the world's first bitcoin transaction.

The value of the first bitcoin transactions were negotiated by individuals on
the bitcointalk forums with one notable transaction of 10,000 BTC used to indirectly
purchase two pizzas delivered by Papa John's.

#### Technical details

Bitcoin is built on the technology called *blockchain*. Blockchain is a
continuously growing list of records, called blocks, which are linked and secured
using cryptography.

![The blockchain]({{ "/assets/images/bc.jpeg" | absolute_url }}){:width="700px"}

The bitcoin blockchain is a huge public ledger (over 136 GB as of October 2017),
keeping records of all the transactions happening within the system.

The network consists of many mutually distrustful parties that are called “miners”,
who are together responsible for guaranteeing the integrity of the system and the
validity of transactions. A miner is someone who is willing to offer computational
power to validate transactions, add them to a block and add that block to the chain.
To do that, the miner must offer proof of work, a solution to a very hard
mathematical equation, using cryptography. In exchange, the miner who proofs the
equation and adds the block to the system is rewarded with freshly minted bitcoins.

The block reward is the only way that new bitcoins are created on the network.
*Satoshi* explained this in an early email post in 2009:

>  “Coins have to get initially distributed somehow, and a constant rate seems like
the best formula.” - *Satoshi*

The block reward started at 50 BTC in block # 1 and halves every 210,000 blocks.
This means every block up until block # 210,000 rewards 50 BTC, while block 210,001
rewards 25.

Eventually, the reward will decrease to zero, and the limit of 21 million bitcoins
will be reached by 2140; the record keeping will then be rewarded by transaction
fees solely.

>  “In a few decades when the reward gets too small, the transaction fee will
become the main compensation for nodes.” - *Satoshi*

when a user spends some money, a transaction is broadcast to the network,
all miners collect the latest transactions and insert them in blocks,
each miner then tries to solve the mathematical equation before all other miners,
the miner who successfully solves the equation broadcasts the newly "mined" block
to the network, and that block is added to the block chain, the successful miner
is rewarded some newly minted bitcoins.

Each block in the block chain contains a certain number of transactions, as well
as a hash, which points to the previous block in the block chain, this means that
as chain progresses, older blocks become more secure, they can't be tampered with,
because to change a block, or one transaction within a block, an attacker must
mine new blocks and attach them to the tampered block, in which case he has
created a new branch of the chain, and he must continue building his branch in
a rate faster than the original branch of the network, for his branch to be
considered legitimate. an attacker can theoretically achieve this if he owns
more than 50% of the computing power in the network, which is impossible.

![Blockchain attack]({{ "/assets/images/bc-attack.png" | absolute_url }}){:width="700px"}

## Other applications for the Blockchain technology

Blockchain can change many industries and systems other than the monetary system,
any Industry that needs a reliable record of data that must be secure and trusted can
benefit a lot from Blockchains.

In December 2015, the Linux Foundation announced the creation of the [Hyperledger](https://en.wikipedia.org/wiki/Hyperledger){:target="_blank"} Project,
which is an umbrella project of open source blockchains and related tools. many
companies are members of the project, including IBM, RedHat, VMWare, Intel...

Blockchain today is [used by Maersk in collaboration with IBM](https://www-01.ibm.com/common/ssi/cgi-bin/ssialias?htmlfid=CPV03008USEN){:target="_blank"}
to digitize and simplify global trade and offer transparency in the shipping industry.

[Walmart is working with IBM](https://www.youtube.com/watch?v=SV0KXBxSoio){:target="_blank"}
to offer a way for shoppers to trace back the history of the food they are buying
from when it was planted until it reached them.

The [Real estate industry](https://venturebeat.com/2017/11/18/blockchain-could-change-everything-for-real-estate/){:target="_blank"} is also expected to benefit from the blockchain technology, by virtue of
smart contracts, a system where contracts are activated automatically when their conditions
are met. blockchain can offer as well a reliable record for real estate ownership within
a city.

One thing is clear, The Blockchain technology is a game changer, a technology that will
affect many industries positively in the coming years.