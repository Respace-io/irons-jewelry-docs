---
layout: post
icon: fas fa-code
order: 11
toc: true
---

## Introduction

Atlas API is a 1.21+ NeoForge API for generating [atlases](/atlas-api/#what-is-an-atlas) during game runtime, with
data-driven textures in
mind. Atlas API handles all atlas management behind the scenes automatically, and provides a custom model loader that
allows the user to create dynamic item models from their atlas sprites. Atlas API also handles all model caching,
clearing, and texture reloads; all you do is tell the API where your textures are, and basic model instructions.

<a href="https://discord.gg/TRzEdrndM2"><img src="https://img.shields.io/discord/1104430139275743293.svg?label=&amp;logo=discord&amp;logoColor=ffffff&amp;color=7389D8&amp;labelColor=6A7EC2&amp;style=for-the-badge" alt="" width="129" height="28" /></a>

## Dependency Setup

In order to build against Atlas API, you need to configure your `build.gradle` file.
You will need as least one of the following mavens under `repositories`.
If you are not interested in building with snapshots, you only need the release maven.

```groovy
maven {
  name = "Iron's Maven - Release"
  url = "https://code.redspace.io/releases"
}
maven {
  name = "Iron's Maven - Snapshots"
  url = "https://code.redspace.io/snapshots"
}
```

In order to include the api in your project, add the following under `dependencies`:

```groovy
compileOnly "io.redspace:atlas_api:${atlas_api_version}:api"
localRuntime "io.redspace:atlas_api:${atlas_api_version}"
```

This assumes you have gradle variable `atlas_api_version` setup. Additionally, you may want to use the Atlas Viewer mod
when developing to see your dynamic
atlas: [curseforge.com/minecraft/mc-mods/atlasviewer](https://www.curseforge.com/minecraft/mc-mods/atlasviewer)

### Example Repo

If you are looking for an example of the API in action, you can look at Iron's Gems 'n Jewelry, the mod this API was
developed alongside of:
[https://github.com/iron431/irons-jewelry](https://github.com/iron431/irons-jewelry)

## Asset Handler

The entrypoint of Atlas API is your `AssetHandler`. These must be registered, and each registered asset handler
automatically gets paired with a dynamic atlas. There is exactly one dynamic atlas per handler, and a handler is the
only way to get a dynamic atlas. The implementation of its methods is how you instruct the API to build your atlas and
stitch your models. All access to your sprites is done through your asset handler.

```java
public class ExampleHandlerRegistry {
  private static final DeferredRegister<AssetHandler> HANDLERS = DeferredRegister.create(AtlasApiRegistry.ASSET_HANDLER_REGISTRY_KEY, ExampleMod.MODID);

  public static final Supplier<ExampleAssetHandler> MY_HANDLER = HANDLERS.register("my_handler", ExampleAssetHandler::new);

  public static void register(IEventBus eventBus) {
    HANDLERS.register(eventBus);
  }
}
```

### Sprite Sources

```java
public abstract class AssetHandler {
  //...
  public abstract List<SpriteSource> buildSpriteSources();
  //...
}
```

In order for Atlas API to build an atlas for you, you must implement `AssetHandler#buildSpriteSources`. It is called the
first time the game attempts to access your atlas during runtime (most often when one of your items renders).
* * *
A `SpriteSource` is a vanilla Minecraft structure, and tells an atlas how to convert files into sprites. Some common
sprite sources are `SingleFile`, `DirectoryListener`, or `PalettedPermutations`. Some additional information is covered
on the Minecraft wiki: [minecraft.wiki/w/Atlas](https://minecraft.wiki/w/Atlas).
* * *
No additional context is provided in this method's parameters;
it is up to you to build your own sprite sources, such as by reading through a registry or datadriven files.

### Baked Model Preparations

```java
public abstract class AssetHandler {
  //...
  BakingPreparations makeBakedModelPreparations(ItemStack itemStack, @Nullable ClientLevel clientLevel, @Nullable LivingEntity livingEntity, int seed);
  //...
}
```

Atlas API provides a custom [model loader](/atlas-api/#model-loader) that can utilize your dynamic sprites in an item
model. In order for Atlas API to construct these dynamic models for you, you must
implement `AssetHandler#makeBakedModelPreparations`. In this method, you are provided the standard item baking context,
including the
ItemStack being rendered. This is called whenever an ItemStack yielding a unique [model ID](/atlas-api/#model-id) is
rendered for the first
time. The baked model it produces is cached. The `BakingPreparations` record which is returned simply contains a list
of `ModelLayer` records. The `ModelLayer`
record is a grouping of data pertaining to rendering a single sprite:

`ModelLayer(ResourceLocation spriteLocation, int drawOrder, Optional<Transformation> transformation)`

`spriteLocation` is a resource location that points to an entry on your atlas. This is provided and maintained by you (
these are the resource locations you created in `AssetHandler#buildSpriteSources`). `drawOrder` determines the draw
order of your layers; the lowest draw order is drawn first. `transformation` is an optional input of
Minecraft's `Transformation` class. This can move, scale, or rotate your sprites. If none is specified, no translations,
scalings, or rotations are applied to this layer.

### Model ID

```java
public abstract class AssetHandler {
  //...
  public abstract int modelId(ItemStack itemStack, @Nullable ClientLevel clientLevel, @Nullable LivingEntity livingEntity, int seed);
  //...
}
```

In order to differentiate when the API should bake a new model for you, you must implement `AssetHandler#modelId`. You
have the same parameters as `AssetHandler#makeBakedModelPreparations`, because these methods are used in tandem. You
should implement an algorithm that produces a unique and deterministic value for every unique model to display. For
example, if your model is driven by an item component, the id should be the item component's hash code. This ID is
stored in conjunction with your modid, so you do not need to worry about competing ids with other mods (only yourself).

## Model Loader

Atlas API provides a custom item model geometry loader to acess your dynamic sprites: `atlas_api:dynamic_model`
In order to actually use the dynamic baking features of your `AssetHandler`, you must use this geometry loader in your
item model definitions, and give it the registered name of your asset handler under the `handler` field.
For example, as per our [example registered handler](/atlas-api/#asset-handler):

```json
{
  "parent": "minecraft:item/generated",
  "loader": "atlas_api:dynamic_model",
  "handler": "examplemod:my_handler"
}
```

In practice, this is a very simple geometry loader, akin to the `minecraft:builtin/generated` layered model, but with
access to Atlas
API's dynamic atlas sprites. You can always implement your own loader to meet more advanced rendering requirements, and
obtain your sprites via your [asset handler](/atlas-api/#asset-handler). More about geometry loaders can be found
here: [https://docs.neoforged.net/docs/resources/client/models/modelloaders/](https://docs.neoforged.net/docs/resources/client/models/modelloaders/)

## What is an Atlas?

This is usually done to for game performance, where instead of loading separate texture files, only one atlas file is
loaded, and the game knows how to find a specific texture on it. More about generic texture atlases can
Atlas API allows for runtime generated atlases, so what is an Atlas? Also known as a spritesheet, an Atlas is a term in
computer graphics that refers to a single large texture that is made up of many smaller textures stitched together.
be [read here](https://en.wikipedia.org/wiki/Texture_atlas).
* * *
Minecraft's atlases are generated when the game loads, or when textures are reloaded. This means they are completely
rigid and must be configured in advance, usually before the game launches, by a mod or by a texture pack. However, with the advent of
Minecraft's palette system (seen in armor trims), there is a growing use-case for dynamic textures generated at
runtime, especially those based on datapacks or other data-driven resources. This is where Atlas API
comes [into play](/atlas-api/#introduction). Below are examples of Minecraft texture atlases: 
### Minecraft Block Atlas (Fixed at texture load)
![Minecraft Block Atlas](/img/screenshots/minecraft_block_atlas.png)
### Iron's Jewelry Atlas (Datadriven Atlas API Atlas)
![Irons Jewelry Atlas](/img/screenshots/irons_jewelry_atlas.png)

