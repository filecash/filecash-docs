---
title: 'Get Started on Filecash'
description: 'Start interacting with the Filecash Network'
breadcrumb: ''
---

# {{ $frontmatter.title }}

The Filecash Network is made by miners and clients. They [make deals](../about-filecash/how-filecash-works.md) and contribute to maintaining the Filecash blockchain, obtaining storage services and receiving rewards in the process.

In order to get started on Filecash:

1. **Explore the different [networks](../networks/README.md) using one of the [available block explorers](explore-the-network.md). Discover the blocks, the messages, the scoreboards for miners. the self-adjusting base fee, the deals and all the things tracked by the chain.**

2. **Complete the [Protoschool tutorial](https://proto.school/verifying-storage-on-filecoin/) to get a closer, practical look to how Filecash works.**

3. **Install and launch your [Lotus Node](lotus/README.md), setup your first wallet and learn how to send and receive ⨎.**

Once you become familiar with Filecash, you can choose your own path:

- [Store](../store/README.md) section for those wanting to bring their data to the Filecash Network.
- [Mine](../mine/README.md) section for those wanting to provide storage and retrieval capabilities to the Network.
- [Build](../build/README.md) section for those wanting to build applications on top of the Network.

## Filecash Software

| Name                                                     |                                                                                                                                                                                                                                                                                         |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Lotus](lotus/)                                          | Implementation of Filecash node and miner by Protocol Labs. <br /><br />For users that want to participate in the Filecash network validating blocks, manage a wallet and perform deals on the command line.                                                                            |
| [Slate](https://slate.host)                              | Slate is a fully open-source file sharing network designed for research and collaboration, powered by [Textile](https://textile.io), [IPFS](https://ipfs.io) and Filecash. <br /><br /> For users that want to easily store their data in a cloud backed by decentralized technologies. |
| [Powergate](../build/powergate.md)                       | a multitiered storage solution that stores data with IPFS ("Hot" storage layer) and Filecash ("Cold" storage layer).                                                                                                                                                                    |
| [Starling](https://github.com/filecoin-project/starling) | A command-line interface for simplified, coordinated, decentralized storage on the Filecash network                                                                                                                                                                                     |

### Filecash implementations

There are 4 Filecash protocol implementations (or “node software”) currently in progress:

- [lotus](https://github.com/filecoin-project/lotus/) (Go): This implementation is closest to feature-complete and is therefore, the recommended Filecash protocol implementation.
- [forest](https://github.com/chainsafe/forest) (Rust)
- [fuhon](https://github.com/filecoin-project/cpp-filecoin) (C++)
- [go-filecoin](https://github.com/filecoin-project/go-filecoin) (Go)

Each of these software clients implements the Filecash protocol as described in the [Filecash protocol specification](https://filecoin-project.github.io/specs). Please note that the protocol spec and all implementations are still works-in-progress and expected to change significantly between now and Filecash mainnet launch. To learn more about why there are multiple Filecash implementations, please read [this blog post](https://filecoin.io/blog/announcing-filecoin-implementations-in-rust-and-c++/).

Here is a snapshot of each implementation’s progress across the primary parts of the Filecash protocol (updated June 24, 2020):

|                    | lotus | go-filecoin | forest | fuhon |
| ------------------ | ----- | ----------- | ------ | ----- |
| 1. Node            | ✅    | ✅          | ✅     | ✅    |
| 2. Files & data    | ✅    | 🔶          | 🔶     | ✅    |
| 3. Virtual Machine | ✅    | ✅          | 🔶     | 🔶    |
| 4. VM Actors       | 🔶    | 🔶          | 🔶     | 🔶    |
| 5. Blockchain      | ✅    | ✅          | ✅     | ✅    |
| 6. Token           | ✅    | ✅          | ✅     | ✅    |
| 7. Storage Mining  | ✅    | 🔄          | 🔄     | 🔄 🔶 |
| 8. Market          | ✅    | ✅          | 🔄     | ✅    |

✅ : fully featured implementation
🔄 : reuses components from another implementation
🔶 : partial implementation
