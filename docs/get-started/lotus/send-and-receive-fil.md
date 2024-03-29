---
title: 'Lotus: send and receive FIL'
description: 'This guide will show you how to create and manage a Lotus wallet and how to use it to send some Filecash to a different address.'
breadcrumb: 'Send and receive ⨎'
---

# {{ $frontmatter.title }}

{{ $frontmatter.description }}

In order to receive and send FIL with Lotus you will need to have [installed and be running a Lotus Node](installation.md).

[[TOC]]

## Creating a wallet

```bash
lotus wallet new bls
```

This will print your Filecash address.

::: tip
Your wallet information is stored in the `~/.lotus/keystore` (or `$LOTUS_PATH/keystore`). For instructions on export/import, see below.
:::

You can create multiple wallets and list them with:

```bash
lotus wallet list
```

## Obtaining FIL

FIL can be obtained either by using one of the Faucets (check URLs in the [Networks dashboard](https://networks.filecoin.io) or by buying it from an exchange supporting FIL trading (once mainnet has launched).

Once you have received some FIL you can check your balance with:

```bash
lotus wallet balance
```

Remember that your will only see the latest balance when your daemon is fully synced to the current tip of the chain.

## Sending FIL

Send FIL from the default wallet by running:

```bash
lotus send <target address> <amount>
```

To get the current default wallet address:

```bash
lotus wallet default
```

To set the default wallet address to a different address:

```bash
lotus wallet set-default <address>
```

To send FIL from a specific wallet:

```bash
lotus send --from=<sender address> <target address> <amount>
```

:::tip
Make sure to check `lotus send --help` for advanced options.
:::

## Exporting and importing a wallet

::: warning
Keep your wallets' private keys safe!
:::

You can export and re-import a wallet, potentially to a different Lotus node, with:

```bash
lotus wallet export <address> > wallet.private
```

and:

```bash
lotus wallet import wallet.private
```

::: tip
If one of the nodes is offline, copying the files in `~/.lotus/keystore` directly should also work.
:::
