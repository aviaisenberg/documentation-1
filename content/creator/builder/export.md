---
date: 2018-02-11
title: Export as code
description: Export a scene as code to work on it using the SDK.
categories:
  - builder
type: Document
aliases:
  - /builder/export/
url: /creator/builder/export
---

You can start a scene with the Builder, and then make it more interactive by writing code with the SDK (Software Development Kit).

The Builder uses the Decentraland SDK under the hood, generating the required code without you ever needing to look at it. If you export the scene, then you can alter its code directly.

To export a scene, open the scene and click the export icon.

![](/images/media/builder-export.png)

This will export the scene as a .zip file. This zip file will contain all of the required code and supporting files to run the scene, including 3D models, sound files, etc.

See [SDK 101]({{< ref "/content/creator/scenes/getting-started/sdk-101.md" >}}) if you're not yet familiar with coding with the Decentraland SDK.

## Workflow

Start your scene in the Builder, and only export it when you're sure you won't be making any more changes to it from the Builder.

Once you modify your scene with the SDK, you can’t import those changes back into the Builder. You can only go from the Builder to the SDK, not in the other direction.

{{< hint warning >}}
**📔 Note**   If you attempt to reimport the scene into the Builder, the only file in the project folder that is considered is the `builder.json` file, that was generated when exporting from the Builder. Any changes you did to other files, like `game.ts`, are ignored when importing.
{{< /hint >}}

Alternatively, you can keep all SDK changes in a neat section of your code, and manually paste these into newly exported versions of the Builder scene as you iterate it.

## Smart items

If the scene contains smart items, each smart item is exported as a separate folder that contains all the supporting code, 3D models, sound files, etc. These smart item folders are named using the smart item's hash, for example _1fc96600-3d45-45f6-b364-86aa8cd15587_.

You can modify the code for a smart item by changing the item's `item.ts` file. Keep in mind that this will change all of the instances of that smart item in the scene.

## Rotating a scene

When exporting a scene, it's always exported with the default orientation.

You may need to rotate the scene so that it better fits your land, especially for the case of scenes that are not square. The easiest way to do this is to edit the scene's `src/game.ts` file to rotate the `scene` entity. This entity is a parent to everything else in the scene, so all the items in the scene will rotate with it.

Since the `scene` entity rotates around the 0,0 point of the scene (the bottom-left corner), you will also need to shift the `scene` entity so that it aligns with the scene again.

The following example rotates a 2x1 scene so that it fits a 1x2 space. It rotates the whole scene 90 degrees, and then shifts it one parcel to the right to re-center the scene:

```ts
const _scene = new Entity("_scene")
engine.addEntity(_scene)
const transform = new Transform({
  position: new Vector3(0, 0, 16),
  rotation: Quaternion.Euler(0, 90, 0),
  scale: new Vector3(1, 1, 1),
})
_scene.addComponentOrReplace(transform)
```

See [Entity positioning]({{< ref "/content/creator/scenes/3d-essentials/entity-positioning.md" >}}) for more details on how to move and rotate items.
