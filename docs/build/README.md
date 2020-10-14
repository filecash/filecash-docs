---
title: Build
description: Documentation to start building applications on Filecash.
---

# Build

Filecash is for the builders. If you are excited about the potential of leveraging the Filecash protocol and decentralized storage network to build game-changing applications, you've come to the right place.

[[TOC]]

## Onboard the testnet

The Filecash testnet is a network with parameters and activity levels _as close as possible_ to the expected state of the Filecash mainnet once it launches. To get up to speed quickly on how to start storing data on the testnet, check the [onboard the testnet](onboard-testnet.md) guide.

## Filecash-backed storage providers

The following products provide storage solutions that are backed up by the Filecash network and potentially [integrate IPFS as a hot-data layer (FPS)](filecash-pinning-services.md).

::: tip
We plan to update this list regularly as new providers are announced and their features expand.
:::

| Name                                                | Description                                                                                                                   | [IPFS Pinning API](https://ipfs.github.io/pinning-services-api-spec/) support |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [Textile Buckets](https://docs.textile.io/buckets/) | A hosted service that allows development teams to build software projects end-to-end on a decentralized DB and storage stack. | No                                                                            |
| **Chainsafe**                                       | Coming soon.                                                                                                                  | No                                                                            |
| [Pinata](https://pinata.cloud)                      | IPFS pinning service, with Filecash coming soon.                                                                              | No                                                                            |

For more information about the benefits and the architecture of Filecash-backed Pinning Services, check the [FPS page](filecash-pinning-services.md).

## Hosted nodes

Hosted node providers take care of running Filecash node software for you so that you can focus on integrating and building on top of it.

| Name                                                          | Description                                                                                                                                                                                       | [IPFS Pinning API](https://ipfs.github.io/pinning-services-api-spec/) support |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| [Hosted Powergate](https://blog.textile.io/hosted-powergate/) | The Textile team offers hosted [Powergate](./powergate.md) instances. Read the announcement [here](https://blog.textile.io/announcing-managed-powergate-instances-enterprise-filecoin-and-ipfs/). | No                                                                            |
| [Lotus hosted nodes](lotus/hosted-nodes.md)                   | Protocol Labs in partnership with [Protofire](https://protofire.io) provides hosted Lotus instances accessible via the Lotus JSON-RPC API endpoint.                                               | No                                                                            |

## Developer references

The following documentation links can help you start building on Filecash:

| Name                                       | Description                                                                                                                                                                                                                                                                 |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Building on Lotus](lotus/README.md)       | Lotus nodes provide JSON-RPC API with JWT-token-based authorization.                                                                                                                                                                                                        |
| [Powergate](powergate.md)                  | Powergate is a multitiered storage solution that stores data with IPFS and Filecash.                                                                                                                                                                                        |
| [Local devnet](local-devnet.md)            | Learn how to deploy a Filecash network fully contained on your own computer.                                                                                                                                                                                                |
| [Application examples](examples/README.md) | Create your own Filecash powered applications following one of our examples: [Simple pinning service](examples/simple-pinning-service/overview.md), [Network inspector](examples/network-inspector/overview.md), [Meme marketplace](examples/meme-marketplace/overview.md). |

## Additional resources

- [Filecash integrations for web3 infrastructure](https://www.youtube.com/watch?v=Q0oe6i7d1u4) (video)
- [What is an IPFS Pinning Service?](https://medium.com/pinata/what-is-an-ipfs-pinning-service-f6ed4cd7e475#:~:text=An%20IPFS%20pinning%20service%20is,running%20your%20own%20IPFS%20nodes.) (Pinata explainer)
- [IPFS Docs: Persistence, permanence and pinning](https://docs.ipfs.io/concepts/persistence/)
- [Developing on Filecash](https://www.youtube.com/watch?v=aGCpq0Xf-w8) (video)
- Textile tools: [video](https://www.youtube.com/watch?v=IZ8M9m9_uJY) and [blog post](https://blog.textile.io/developer-tools-for-filecoin-ipfs-web/)
- [Building decentralized apps using Fleek’s Space daemon](https://www.youtube.com/watch?v=pWJ5fty-7mA) (video)
