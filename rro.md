# Recommended Reading Order

## Bitcoin White Paper

https://bitcoin.org/bitcoin.pdf

The OG cryptocurrency. Covers

- How Proof of Work offers security, and the incentives involved
- The block/transactions model (ubiquitous in most cryptocurrencies)
- The UTXO abstraction
- SPV client vs Full Node

The diagram on page 2 is quite confusing, I like Joao Batalha's clarification at https://fermatslibrary.com/s/bitcoin

On a first readthrough, I would focus on the game theory / cryptoeconomics behind PoW, and why cryptograph without cryptoeconomics can't solve the problem of decentralized currency, skipping the details about UTXOs and light clients.

## Ethereum White Paper

https://github.com/ethereum/wiki/wiki/White-Paper

Describes ethereum. Also describes Bitcoin at about the same level of detail as Satoshi's paper, but with a slightly different abstraction, which might help.

- What smart contracts are and why they might be useful
- The EVM, accounts and storage
- Using GHOST to reduce "wasted" hashpower

## Introduction to Blockchain Scaling

https://hackernoon.com/blockchains-dont-scale-not-today-at-least-but-there-s-hope-2cb43946551a

Covers what the scaling problem is - why exactly is there a really low transactions-per-second cap, between 5 and 50, on both ETH and BTC? - and an overview of some solutions.

## Scalability, Part 1: Building on Top

https://blog.ethereum.org/2014/09/17/scalability-part-1-building-top/

These posts are well-written but presume a lot of previous knowledge (like most of Vitalik's writing), so I hesitate to put them here, but scalability is such an important problem that it is a good idea to start thinking in detail about how to solve it - and the previous post misses some solutions. Vitalik's 3-part blog post is a bit old and certainly not comprehensive, but it's a good place to start skimming.

Here are part 2 and 3, but they are more skippable

https://blog.ethereum.org/2014/10/21/scalability-part-2-hypercubes/
https://blog.ethereum.org/2014/11/13/scalability-part-3-metacoin-history-multichain/

## The Bitcoin Lightning Network: Scalable Off-Chain Instant Payments

https://lightning.network/lightning-network-paper.pdf

On-chain and off-chain methods for scaling are largely orthogonal. A lot of the paper is dedicated to implementing lightning networks using Bitcoin opcodes, which being non-Turing-complete are quite awkward to use.

## Proof of Stake: How I Learned to Love Weak Subjectivity

https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/

Proof of Stake is very controversial outside of the ethereum community. There are no really good resources about it, but this post has good descriptions on two important problems - nothing-at-stake and long-range attacks - as well as how Ethereum plans to solve them. It also presents why PoS can have better security than PoW and one seemingly inescapable problem with any PoS, the whole subjective checkpoint business.

The post has arguments on a more conceptual level - if you want concrete details, https://ethresear.ch/t/latest-casper-basics-tear-it-apart/151

## A Prehistory of the Ethereum Protocol

http://vitalik.ca/general/2017/09/14/prehistory.html

I think this is a good point (perhaps even overdue) to learn about the history of Ethereum, to understand which parts are fundamental decisions and which are path-dependent accidents. Also a very well written story.

## Secret Sharing and Erasure Coding: A Guide for the Aspiring Dropbox Decentralizer

https://blog.ethereum.org/2014/08/16/secret-sharing-erasure-coding-guide-aspiring-dropbox-decentralizer/

It's not like the problem of writing a decentralized dropbox is THE killer app for blockchains, but this post goes into a lot of detail and describes the actual problems you have to solve to build a decentralized dropbox. Writing dapps and getting the incentive structure correct is hard - a lot of people think you can put anything on it by magic.
