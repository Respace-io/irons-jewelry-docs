---
layout: post
icon: fas fa-code
order: 12
toc: true
---

## Introduction

Atlas API is a 1.21+ NeoForge API for generating [atlases](/atlas-api/#further-reading-what-is-an-atlas) during game runtime, with
data-driven textures in
mind. Atlas API provides an easy-to-use layer of abstraction around all atlas management, and provides custom model
loaders that
allows the user to create dynamic item models from their dynamic sprites. Atlas API also handles all model caching,
clearing, and texture reloads.

<a href="https://discord.gg/TRzEdrndM2"><img src="https://img.shields.io/discord/1104430139275743293.svg?label=&amp;logo=discord&amp;logoColor=ffffff&amp;color=7389D8&amp;labelColor=6A7EC2&amp;style=for-the-badge" alt="" width="129" height="28" /></a>

## Dependency Setup

In order to build against Atlas API, you need to configure your `build.gradle` file.
You will need at least one of the following mavens under `repositories`.
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

Additionally, you may want to use the Atlas Viewer mod
when developing to see your dynamic
atlas: [curseforge.com/minecraft/mc-mods/atlasviewer](https://www.curseforge.com/minecraft/mc-mods/atlasviewer)

### Example Repo

If you are looking for an example of the API in action, you can look at Iron's Gems 'n Jewelry, the mod this API was
developed alongside of:
[https://github.com/iron431/irons-jewelry](https://github.com/iron431/irons-jewelry)

## Asset Handler

The entrypoint of Atlas API is your `AssetHandler`. These must be registered, and each registered asset handler
automatically gets paired with exactly one dynamic atlas, managed by Atlas API. The implementation of its methods is how you instruct the API to build your atlas and
stitch dynamic models. All access to your sprites is done through your asset handler.

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
class AssetHandler {
  List<SpriteSource> buildSpriteSources();
}
```

In order for Atlas API to build an atlas for you, you must implement `AssetHandler#buildSpriteSources`. It is called on world load, giving you access to world-specific information, such as datapacks.
* * *
A `SpriteSource` is a vanilla Minecraft structure, and tells an atlas how to convert files into sprites. Some common
sprite sources are `SingleFile`, `DirectoryListener`, or `PalettedPermutations`. Some additional information is covered
on the Minecraft wiki: [minecraft.wiki/w/Atlas](https://minecraft.wiki/w/Atlas).
* * *
No additional context is provided in this method's parameters;
it is up to you to build your own sprite sources, such as by reading through a registry or datadriven files.

### Baked Model Preparations

```java
class AssetHandler {
  BakingPreparations makeBakedModelPreparations(ItemStack itemStack, @Nullable ClientLevel clientLevel, @Nullable LivingEntity livingEntity, int seed);
}
```

In order to use the Dynamic Model [model loader](/atlas-api/#dynamic-model-loader), you must
implement `AssetHandler#makeBakedModelPreparations`. In this method, you are provided the standard item baking context,
including the
ItemStack being rendered. This is called whenever an ItemStack utilizing an `atlas_api:dynamic_model` that yields a
unique [model ID](/atlas-api/#model-id) is
rendered for the first
time. The resulting model is automatically cached. `BakingPreparations` is a record containing a list
of `ModelLayer`'s. The `ModelLayer`
record holds data for rendering a single sprite:

`ModelLayer(ResourceLocation spriteLocation, int drawOrder, Optional<Transformation> transformation)`

The `spriteLocation` is a resource location that points to an entry on your atlas. These are the resource locations you created in `AssetHandler#buildSpriteSources`,
and thus are provided and maintained by you. `drawOrder` determines the draw
order of your layers; the lowest draw order is drawn first. `transformation` is an optional input of
Minecraft's `Transformation` class. This can move, scale, or rotate your sprites. If none is specified, no translations,
scalings, or rotations are applied to this layer.

### Model ID

```java
class AssetHandler {
  int modelId(ItemStack itemStack, @Nullable ClientLevel clientLevel, @Nullable LivingEntity livingEntity, int seed);
}
```

In order to associate different items to different models when using the Dynamic Model loader, you must
implement `AssetHandler#modelId`. You
have the same parameters as `AssetHandler#makeBakedModelPreparations`, because these methods are used in tandem. You
should implement an algorithm that produces a unique and deterministic value for every unique model to display. For
example, if your model is driven by an item component, a good ID might be the item component's hash code. This ID is
stored in conjunction with your modid, so you do not need to worry about competing IDs with other mods (only yourself).

## Model Loaders

Atlas API provides two custom model loaders with access to your sprites: Dynamic Models and Simple Models. You can
always implement your own loader to meet more advanced rendering requirements, and
obtain your sprites via your [asset handler](/atlas-api/#asset-handler). More about custom model loaders can be found
on the [Neoforge Docs](https://docs.neoforged.net/docs/resources/client/models/modelloaders/).

### Dynamic Model Loader

The primary model loader is the Dynamic Model loader: `atlas_api:dynamic_model`. This model loader builds custom models
through code using your
dynamic sprites.
In order to use custom model loaders, you must specify the `loader` field in the item model. Additionally, this loader
requires the registered name of your asset handler under the `handler` field.
For example, as per our [example registered handler](/atlas-api/#asset-handler):

```json
{
  "loader": "atlas_api:dynamic_model",
  "handler": "examplemod:my_handler"
}
```

This is similiar to the `minecraft:builtin/generated` layered model, but with
access to your dynamic sprites, where the layers must be assembled via
code ([`AssetHandler#makeBakedModelPreparations`](/atlas-api/#baked-model-preparations)). While extremely powerful, more
implementation is required on your end, especially in terms of delineating different item types from one another. The
most
optimal use-case for Dynamic Models is when a single item can change texture based on something like item components,
such as modular equipment items.

### Simple Model Loader

Additionally, for simpler use-cases without the need for code, you can use: `atlas_api:simple_model`. This model loader
allows you to reference sprites by name, more closely mimicking vanilla item models, but without
the runtime flexibility code-based models provide.
This means you can use any other vanilla modeling features in this model, including making 3d models.
In order to use custom model loaders, you must specify the `loader` field in the item model. Additionally, this loader
requires the registered name of your asset handler under the `handler` field.
For example, as per our [example registered handler](/atlas-api/#asset-handler):

```json
{
  "loader": "atlas_api:simple_model",
  "handler": "examplemod:my_handler",
  "parent": "minecraft:item/generated",
  "textures": {
    "layer0": "examplemod:item/a_sprite_on_my_atlas"
  }
}
```

This example produces a simple generated model similar to any other model in vanilla, but using a dynamically generated
sprite instead of a fixed texture file.

### Non-Item Sprite Uses

Dynamic sprites are always accessible through `AssetHandler#getSprite` and can be used throughout your code at any time
for non-item usages, such as GUIs or Armor Trims.

## Further reading: What is an Atlas?

Atlas API allows for runtime generated atlases, so what is an Atlas? Also known as a spritesheet, an Atlas is a term in
computer graphics that refers to a single large texture that is made up of many smaller textures stitched together. This
is usually done to for game performance, where instead of loading separate texture files, only one atlas file is
loaded, and the game knows how to find a specific texture on it. More about generic texture atlases can
be [read here](https://en.wikipedia.org/wiki/Texture_atlas).
* * *
Minecraft's atlases are generated when the game loads, or when textures are reloaded. This means they are completely
rigid and must be configured in advance, usually before the game launches, by a mod or by a texture pack. However, with
the advent of
Minecraft's palette system (seen in armor trims), there is a growing use-case for dynamic textures generated at
runtime, especially those based on datapacks or other data-driven resources. This is where Atlas API
comes [into play](/atlas-api/#introduction). Below are examples of Minecraft texture atlases:

### Minecraft Block Atlas (Fixed at texture load)

![Minecraft Block Atlas](/img/screenshots/minecraft_block_atlas.png)

### Iron's Jewelry Atlas (Datadriven Atlas API Atlas)

![Irons Jewelry Atlas](/img/screenshots/irons_jewelry_atlas.png)

