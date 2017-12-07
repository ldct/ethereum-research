# awesome-ethereum-research

This is a list of resources to get a reader up to speed on research behind blockchain fundamental technology (consensus protocols, scalability, privacy, etc), with an emphasis on Ethereum.

# Recommended Reading Order

A lot of stuff is pretty dense so here is my (very biased) list of most important resources to read. I apologize in advance if lots of these are written by Ethereum Foundation members - I definitely intend for this list to include things outside Ethereum's scope like Proof of Storage based consensus - but this is the most "subjective" section and non-ethereum resources appear more in later sections.

## Bitcoin White Paper

https://bitcoin.org/bitcoin.pdf

Yes, this list contains "ethereum" in the title, but we can't ignore the OG cryptocurrency. Read this to understand how Proof of Work offers security, the ubiquitous block/transactions model, and Bitcoin's UTXO abstraction.

## Ethereum White Paper

https://github.com/ethereum/wiki/wiki/White-Paper

Describes a cryptocurrency with Turing complete scripting language. Also describes Bitcoin at about the same level of detail as Satoshi's paper, which might help you get some confusing concepts. Read it to understand what smart contracts are and why they might be useful. It also has some anciliary mostly-orthogonal technical innovations which you should skim or skip for now:

- GHOST-like protocols to reduce "wasted" hashpower
- The account abstraction vs Bitcoin's UTXO abstraction

## Introduction to Blockchain Scaling

https://hackernoon.com/blockchains-dont-scale-not-today-at-least-but-there-s-hope-2cb43946551a

Read this to understand exactly what the scaling problem is - why exactly is there a really low transactions-per-second cap, between 5 and 50, on both ETH and BTC? - and an overview of some solutions.

## On-chain Scaling: Vitalik's Scalability Blog Posts

https://blog.ethereum.org/2014/09/17/scalability-part-1-building-top/
https://blog.ethereum.org/2014/10/21/scalability-part-2-hypercubes/
https://blog.ethereum.org/2014/11/13/scalability-part-3-metacoin-history-multichain/

These posts are well-written but presume a lot of previous knowledge (like most of Vitalik's writing), so I hesitate to put them here, but scalability is such an important problem that it is a good idea to start thinking in detail about how to solve it - and the previous post misses some solutions. Vitalik's 3-part blog post is a bit old and certainly not comprehensive, but it's a good place to start skimming. Feel free to skip parts 2 and 3 for now.

## Off-chain Scaling: Bitcoin Lightning Network

https://lightning.network/lightning-network-paper.pdf

On-chain and off-chain methods for scaling are mostly orthogonal, and this is the OG off-chain scaling paper. I should comment that a lot of the paper is dedicated to implementing lightning networks using Bitcoin opcodes, which being non-Turing-complete are quite awkward to use - so don't worry too much about it.

## Proof of Stake: How I Learned to Love Weak Subjectivity

https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/

Proof of Stake is very controversial outside of the ethereum community. There are no really good resources about it, but this post has good descriptions on two important problems - nothing-at-stake and long-range attacks - as well as how Ethereum plans to solve them. It also presents why PoS can have better security than PoW and one seemingly inescapable problem with any PoS, the whole subjective checkpoint business.

## A Prehistory of the Ethereum Protocol

http://vitalik.ca/general/2017/09/14/prehistory.html

I think this is a good point (perhaps even overdue) to learn about the history of Ethereum, to understand which parts are fundamental decisions and which are path-dependent accidents. Also a very well written story.

## Secret Sharing and Erasure Coding: A Guide for the Aspiring Dropbox Decentralizer

https://blog.ethereum.org/2014/08/16/secret-sharing-erasure-coding-guide-aspiring-dropbox-decentralizer/

It's not like the problem of writing a decentralized dropbox is THE killer app for blockchains, but this post goes into a lot of detail and describes the actual problems you have to solve to build a decentralized dropbox. Writing dapps and getting the incentive structure correct is hard - a lot of people think you can put anything on it by magic.

# Subject-specific recommended reading order

At this point, it is probably better to read by interest instead of through a fixed order. However, I also have recommendations for specific subjects.

## Unanimous-Consent based off-chain scaling

Jeff's State Channel blog posts
Concurrency and Privacy with Payment-Channel Networks

## Fraud-Proof based off-chain scaling

Truebit
plasma.io
Data Availability blog post and videos

## Privacy

Privacy is actually extremely important, but all the resources are very technical.

zerocash paper

## Proof of Stake

Casper-FFG paper
Vlad Zamfir's history of casper

## "Non-linear" blockchains

GHOST, Spectre
Hashgraph

## Sidechains

# Resources

Here are links to resources, grouped by concepts.

# Proof of Work

## 51% attack

If all parties have small hashpower (say <5%) and no way to collude with each other, it is in their economic incentive to work on the longest chain and respect its contraints, and no single party can "rewrite history". If one party controls >51% this is no longer possible.

## <51% attacks

Depending on implementation, there are cases in which a party with a certain hashpower threshold (eg 25% or 33%) is economically incentivized to act differently than if they had very small hashpower.

## ASIC resistant Proof of Work

Application-specific Integrated Circuits (ASICs) encourage centralization. An ASIC resistant PoW tries to make it so that an ASIC does not have much advantage over consumer electronics. One common way is to make the PoW require a lot of memory, as there is no such thing as "application-specific memory".

## Multisignature Wallet

A wallet that requires >1 private key to sign transactions from. https://en.bitcoin.it/wiki/Multisignature

## Reducing Variance

## Useful PoW

## PoPoW

# Privacy

## pseudonomity vs anonymity

The bitcoin network is properly said to be "pseudononymous", since all transactions are forever traceable to an address (or "pseudonym"). This does not translate to real-world anonymity as it is ofter possible to examine the pseudonym's activity and make a good guess as to which real-life person it is. "Privacy-focused" coins like zcash and Monero try to provide real anonymity.

## Mixers/tumblers

A bitcoin address whose operators promise to receive money and send it to an address of your choosing. Someone looking at just the Bitcoin network can't tell that you sent coins from A to B; all they see is coins flowing from A to the mixer, some other users sending coins, and some time later coins flowing from the mixer to B, as well as to other addresses.

## Monero Ring Confidential Transactions

Not sure what this is. Read https://eprint.iacr.org/2015/1098.pdf.

## zero-knowledge proofs (ZKP)

An amazing theorem implies that (quoting Scott Aaronson)

"Supposing you do prove the Riemann Hypothesis, it’s possible to convince someone of that fact, without revealing anything other than the fact that you proved it. It’s also possible to write the proof down in such a way that someone else could verify it, with very high confidence, having only seen 10 or 20 bits of the proof."

You could apply this to, for eg, prove that a particular graph has a certain chromatic number, without helping anyone examining your proof to find the colouring.

## zk-SNARKs

A direct application of ZKPs to provide anonymity, implemented in zcash. Since the constant factors are very big, txs are quite expensive.

# Ethereum Smart Contracts

Generalizes the ad-hoc constructinos behind eg Bitcoin multisig by allowing addresses to be controlled by code written in a Turing-complete language.

## ERC20 Token

An example use case for smart contracts, where a contract mantaints an internal map from ethereum addresses to numbers, representing the balance of some token.

## Gas

Since EVM bytecode is Turing-complete, miners looking at the tx pool don't know ahead of time how long a transaction would take to execute (or even if it will). In the ethereum protocol tx submitters must include a gas cost and limit, and executing contracts require gas. Miners have the right to execute the contract up to the limit and, if the code has not finished executing, they can still include that tx in a block and keep the gas fees.

## More special wallets

Vitalik gave a talk once somewhere where he gave creative generalizations of multisig wallets as a way to showcase the power of Turing-completeness. One example: a contract that allows one private key to initiate send txns and another to cancel them.

## PoW vs PoS

Ethereum currently uses a memory-heavy PoW algorithm and does something different with uncle blocks. They plan to move to PoS in the future.

# Proof of Stake

https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/

## Nothing-at-stake

See above

## Slashing

See above

## Long-range forks

See above

## Security

Assuming all the problems are solved, PoS should be more secure than PoW since in PoW, the most you can penalize someone is to withhold mining rewards, but in PoS you can slash their coins. The market cap of a currency is normally much higher than the economic value of its hashpower (multiplied by some time period).

# Blockchain scaling

Most chains currently support 10-100 tps. Transactions need to scale along two axes: throughput (more tps) and latency (shorter confirmation time). Simply increasing block size and block creation rate improves these metrics up to a point, but after that greatly harm security.

## Bitcoin Lightning Network

https://lightning.network/lightning-network-paper.pdf

Uses multisig and fidelity bonds to allow an off-chain "side chain" between a small set of people. Serialization on the child chain is enforced by allowing participants to punish lying participants by publishing proof-of-fraud to the parent chain, causing the fraudster to lose their bond.

## Sharding

Taipei talk

# Ethereum Off-chain computation

It's really expensive to run computations directly as EVM bytecode. Ethereum off-chain computation projects try to provide an AWS-like service on ethereum. Of course, one needs a way to verify that the computation is correct, without re-running it.

## GNT

Currently has some an ad-hoc way of "cheaply verifying" specific computations as well as some reputation mechanisms.

## Probabilistically Checkable Proof (PCP)

A theorem implying that there exists a way to cheaply (in terms of algorithmic complexity) verify and outsource any computation. Unfortunately the constant factors are currently huge.

http://delivery.acm.org/10.1145/2650000/2641562/p74-walfish.pdf?ip=129.97.125.1&id=2641562&acc=OA&key=FD0067F557510FFB%2E9219CF56F73DCF78%2E4D4702B0C3E38B35%2E757E42EE4C319386&CFID=992301834&CFTOKEN=74894299&__acm__=1507507067_1652419b2c210481337d926c648d2e71

# Ethereum Off-chain storage


# Oracles

An oracle is a way for on-chain contracts to know about "real-world" events (eg the outcome of a football game, the market price of Apple stock, the results of an election). There are a few projects trying to create decentralized oracles (by economically incentivizing a group of actors to be honest).

## Schelling Point

https://en.wikipedia.org/wiki/Focal_point_(game_theory)

One way decentralized oracles might work. Kind of weird.

# Stablecoins

A cryptocurrency whose market value is close to the market value of some fiat currency. Kind of like implementing sovereign monetary policy.

https://blog.ethereum.org/2014/11/11/search-stable-cryptocurrency/

## MKR Collateralized Debt Position

A position that issues stablecoins collateralized by an underlying asset; allows one to go margin long the underlying by using the stablecoin to buy more underlying.

## NuBits

Imagine if MKR CDPs could only be collateralized by MKR.

# Misc

## Coloured coins

https://en.bitcoin.it/wiki/Colored_Coins

Something like Bitcoin's version of ERC20 tokens.

## Merged mining

https://bitcoin.stackexchange.com/questions/273/how-does-merged-mining-work

## DAG-based blockchains

https://medium.com/@avivzohar/the-spectre-protocol-7dbbebb707b5

## Zcash on Ethereum

A research project extend ethereum bytecode with elliptic curve operations so that smart contracts can cheaply verify zcash transactions. In the future, this might allow for anonymous transactions on ethereum, or allow smart contracts to store "private" information, or allow private chains secured by ETH.

# Initial Coin Offerings (ICO)

Fun stuff

# Misc. cryptocurrencies/tokens

## Tezos

Most cryptocurrencies upgrade their protocols (fixing bugs, etc), eg through BIP, EIP. These can sometimes be contentious (eg BCH, ETC/ETH) and in the end the "right chain" is enforced by social/economic consensus. Tezos tries to build protocol upgrades into the protocol itself.

## EoS

Most known for running a year-long ICO

## BAT

Tries to reward users for watching ads. Has some weird KYC restrictions planned to prevent sybil attacks.

## SNT

A strange project
