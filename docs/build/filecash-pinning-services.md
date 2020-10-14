---
title: 'Filecash-backed Pinning Services'
description: "Filecash-backed pinning services (FPS) are data storage and retrieval services that offer the performance and availability of IPFS alongside the data persistence features of Filecash's decentralized storage network."
breadcrumb: 'FPSs architecture'
---

# {{ $frontmatter.title }}

{{ $frontmatter.description }}

::: tip
You can find a list of [existing FPS providers here](README.md).
:::

[[TOC]]

## How to use an FPS

While each FPS provider will have slightly different instructions for utilizing the service, the general flow remains the same:

- Create and configure your account with the FPS provider.
- Retrieve your auth token for the FPS provider.
- Make storage requests through the API of the service you are using.
- Maintain and monitor your data storage.
- Retrieve your data through the API of the service you are using.

## Key benefits of FPSs

1. Data is backed up on the Filecash network for data persistence.

2. Developers do not need to worry about maintaining their own decentralized infrastructure. Using an FPS also avoids _vendor lock-in_, since all providers contribute to the same storage network.

3. FPSs are working towards the adoption of the [IPFS Pinning Service API](https://ipfs.github.io/pinning-services-api-spec/). This common API is designed to work flexibly with any content-addressed storage solution, be it Filecash, IPFS, or a service integrating both. Filecash-specific workflows are abstracted from the users without sacrificing features like different geographies, redundant copies, and cryptographic storage receipts.

## How FPS solutions work

FPS solutions run IPFS (for hot storage) and Filecash (for cold storage) software clients under the hood, either communicating directly with these software clients through their native APIs or through tools like [Powergate](./powergate.md). FPS services manage the flow of data between the different networks, employing intelligent caching strategies to keep popular data readily available.

![Diagram showing a simplified architecture for a Filecash IPFS Pinning Service (FPS). User makes API request to the FPS. The FPS stores and retrieves data from embedded go-ipfs and lotus nodes, which communicate with each other via libp2p and IPLD data formats.](./images/filecash-pinning-services/fps-data-flows.png)

While the specific architecture of each service will look different, most FPS solutions follow similar flows behind-the-scenes.

**Data storage**:

- When a user makes an API request to store a particular CID through an FPS, the FPS will pin that CID to its node (which is connected to the public IPFS network) -- or the “Hot” storage layer.
- The FPS will simultaneously initiate Filecash storage deals (“Cold” storage layer) to persist the data.
- If the user specifies a replication factor greater than 1 for their file (X redundant copies of the data), the FPS will initiate X separate Filecash storage deals for the data.
- The user pays the FPS directly for providing this storage service.

**Data retrieval**:

- When a user makes an API request to retrieve a particular CID through an FPS, the FPS will attempt first to retrieve the CID through the “Hot” storage layer (pinned data on the public IPFS network).
- If this is unsuccessful, the FPS will then retrieve the CID through the “Cold” storage layer (data stored with miners on the Filecash network) and serve it back to the requestor.
- The user pays the FPS directly for providing this retrieval service.

Remember that these flows are hidden from the user and take place behind the scenes. Users will interact with a single interface that abstracts away data flows between systems, node management, and Filecash deal management.
