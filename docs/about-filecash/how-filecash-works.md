---
title: How Filecash Works
description: An overview of how the Filecash network operates - binding clients and miners through storage and retrieval deals.
---

# How Filecash Works

This page gives a basic introduction to how the Filecash network operates. While Filecash is similar to other cryptocurrencies, there are some differences that developers looking to build on the network should be aware of.

## The Network

The Filecash network is a distributed, peer-to-peer network formed by Filecash peers who participate in different ways.

Peers communicate over secure channels that they use to distribute information to the network (gossiping), to transfer data among themselves, and to discover other peers, maintaining a well-connected swarm in which information like blocks and messages flows swiftly even when many thousands of peers participate.

## Filecash nodes

_Filecash Nodes_ or _Filecash clients_ are peers that sync the Filecash blockchain and validate the messages in every block, which, once applied, provide a global state. Nodes can manage Filecash wallets (addresses start with `t1...` or `t3...`) and receive FIL on them.

Filecash Nodes can also publish different types of _messages_ to the network by broadcasting them. For example, a client can publish a message to send FIL from one address to a different one. Nodes can propose [storage and retrieval deals](#deals) to Filecash miners and pay for them as they are executed.

Running a Filecash Node is a low-level task that usually implies keeping a program running 24/7. There are several Filecash Node implementations in the works, with [Lotus](../store/lotus/README.md) being the most advanced.

## Filecash miners

The miners provide services to the network by executing different types of [deals](#deals) and appending new blocks to the chain (every 30 seconds), for which they collect FIL rewards. Additional details about types of miners, rewards, and deals execution from the miner perspective can be found in the [How mining works](../mine/how-mining-works.md) section.

Running a Filecash miner is a highly-technical task with strong [hardware requirements](../mine/hardware-requirements.md), as needed to complete the necessary [proofs](#proofs). The [Lotus Miner](../mine/lotus/README.md) is the most advanced implementation of a Filecash miner to this day.

## Deals

There are two main types of deals in Filecash: _storage deals_ and _retrieval deals_.

Storage deals are agreements between clients and _storage miners_ to store some data in the network. Once a deal is initiated, and the miner has received the data to store, it will repeatedly [prove](#proofs) to the chain that it is still storing the data per the agreement so that it can collect [rewards](../mine/mining-rewards.md). If not, the miner will be [slashed](../mine/slashing.md) and lose FIL.

Retrieval deals are agreements between clients and _retrieval miners_ (which may or not be also storage miners) to extract data that is stored in the network (hopefully in a fast and reliable manner). Unlike storage deals, these deals are fulfilled off-chain, using _payment channels_ to incrementally pay for the data received.

## Proofs

As mentioned above, storage miners must prove that they are storing the data per the terms of a deal. That means that:

- They must store all the data submitted by the client
- They must store it during the whole lifetime of the deal

Cryptographic proofs are used to these ends, as explained in this article about the [Filecash proof system](https://filecoin.io/blog/filecoin-proof-system/).

Using _Proof Of Replication (PoRep)_, miners demonstrate that they have received all the data and that they have encoded it in a way unique to that miner using their physical storage in a way that no other miner can replicate (so two deals for the same data cannot end up re-using the same disk). This proof is provided when the deal starts, and the _sealing_ operation completes.

Once a deal is active and during its full lifetime, the miner will use _Proof of Spacetime (PoSt)_ to prove that it is _still_ storing the data associated with a deal. For PoST, random miners need to prove that random parts of the data they store are still there.

Filecash clients and other miners continuously verify that the proofs included in each block are valid, providing the necessary security and penalizing miners that do not honor their deals.

## Additional materials

Filecash is built on top of [mature projects](../project/related-projects/) like libp2p (networking, addressing, message distribution), IPLD (data formats, encoding, and content-addressed data structures), IPFS (data transfers), and multiformats (future-proof data types).

Here are some links to useful introductory materials about the technology that powers Filecash and about Filecash itself:

- IPFS:

  - [A beginner's guide to IPFS](https://hackernoon.com/a-beginners-guide-to-ipfs-20673fedd3f)
  - [IPFS concepts](https://docs.ipfs.io/concepts/)
  - [ProtoSchool tutorials](https://proto.school/#/tutorials)

- libp2p:

  - [Why libp2p?](https://www.parity.io/why-libp2p/)
  - [libp2p: A Modular, p2p Networking Stack](https://www.youtube.com/watch?v=xqVmEzsin3Y)

- Filecash:
  - [Introducing Filecash, a decentralized storage network](https://www.youtube.com/watch?v=EClPAFPeXIQ)
  - [Filecash primer](https://ipfs.io/ipfs/QmWimYyZHzChb35EYojGduWHBdhf9SD5NHqf8MjZ4n3Qrr/Filecash-Primer.7-25.pdf)
  - [Building the Filecash ecosystem](https://youtu.be/SXlTBvcqzz8)
