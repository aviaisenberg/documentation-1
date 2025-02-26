---
date: 2021-03-9
title: NFTs
description: Display NFTs in your scenes.
categories:
  - builder
type: Document
aliases:
  - /builder/nfts/
url: /creator/builder/nfts
---

You can add NFTs (Non-Fungible Tokens) into your scene, displayed as picture frames.

All image and gif formats that are supported in OpenSea are also supported by Decentraland by picture frames. NFTs in video or audio format are currently not supported. NFTs that also have 3D representations, like Decentraland wearables, are displayed in picture frames as 2D images.

## From your wallet

The easiest way to import an NFT you own is to open the **Collectibles** tab on the right menu, under all the asset pack collections. There you'll see a list of all the valid tokens available in the wallet you're currently using. Simply drag an NFT into your scene, you can then move or scale it and treat it like any other item.

![](/images/media/builder-nfts.png)

{{< hint warning >}}
**📔 Note**   The limitation of this approach is that you can only add NFTs that you own, and you can't configure properties of the picture frame, like style of the frame an background color.
{{< /hint >}}

## NFTs By id

The more robust approach is to use the NFT smart item, that you can find in the **Gallery** asset pack, or by simply searching _NFT_ in the search bar above. Once you drag a copy of the NFT item to your scene and select it, there are a few fields that your can configure.

![](/images/media/builder-nft-smart-item.png)

The main fields to configure determine what NFT to display:

- **NFT ID**: The unique id of this specific NFT
- **NFT Contract**: The contract address of the collection that this NFT belongs to (ie: Cryptokitties, SuperRare, Decentraland Halloween Wearables 2019, etc)

To obtain these, the simplest way is to look them up in the Decentraland Marketplace and then check the URL. For example, from the URL of the following item:

_https://market.decentraland.org/contracts/0xb932a70a57673d89f4acffbe830e8ed7f75fb9e0/tokens/20175_

You can infer that the contract is _0xb932a70a57673d89f4acffbe830e8ed7f75fb9e0_ (referring to SuperRare) and the ID is _20175_.

Similarly, you can also obtain these from the OpenSea URL of the token. For example, from the URL of the following item:

_https://opensea.io/assets/0x31385d3520bced94f77aae104b406994d8f2168c/2614_

Yon can infer that the contract is _0x31385d3520bced94f77aae104b406994d8f2168c_ (referring to CryptoPunks) and the ID is _2614_.

Other optional fields that can be configured in this UI:

- **Frame Style**: The default frame style has a glowing margin that might not match the style of the artwork or your scene. There are several other options to pick from with varying styles, from barroque to minimalist, or even tape on the painting's corners.
- **Background Color**: NFTs with transparent background are given a background color, violet by default. You can choose any other color. Note that some frame styles, like _None_, don't include a background color at all. -**Include UI**: When players click on a picture frame, they see a UI with additional information about the token, including creator, description, sale info and links to purchase it. A hint text appears on screen when pointing at the image, which some might consider distracting from the art. Disable the UI to also remove the hint text. -**Extra UI Text**: The UI extracts most of its data from external sources, but allows for an additional field where you can add a custom description. This text is only available to players if _Include UI_ is switched on.

{{< hint warning >}}
**📔 Note**   You can only see these changes take effect when entering the scene in Preview mode. None of these changes modify the representation of the smart item that you drag around in edit mode.
{{< /hint >}}