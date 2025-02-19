---
layout: post
icon: fas fa-code
order: 11
toc: true
---

⚠️This page is Work in Progress! ⚠️ If you're looking for developmental help or want to shape the roadmap, you can join us on Discord:

<a href="https://discord.gg/TRzEdrndM2"><img src="https://img.shields.io/discord/1104430139275743293.svg?label=&amp;logo=discord&amp;logoColor=ffffff&amp;color=7389D8&amp;labelColor=6A7EC2&amp;style=for-the-badge" alt="" width="129" height="28" /></a>

## Addon vs Datapack

This mod is already highly configurable through datapacks, including making new patterns, parts, materials; as well as the configuration of patterns, parts, and materials within the preexisting content of the mod.

An addon gives much more ability to implement new content, such as:
- Jewelry Types
- Bonus Types
- Action Types
- Pattern, Part, and Material data generators

Find more information on creating datapacks on the [data format](/data-format/) page.

## Dependency Setup

In order to build against Gems 'n Jewelry, you need to configure your `build.gradle` file.
You will need the following maven under `repositories`:

```groovy
maven {
  name = "Iron's Maven - Release"
  url = "https://code.redspace.io/releases"
}
```

And you will need the following under `dependencies`:

```groovy
implementation "io.redspace:irons_jewelry:${irons_jewelry_version}"
```

⚠️This page is Work in Progress! ⚠️ If you're looking for developmental help or want to shape the roadmap, you can join us on Discord:

<a href="https://discord.gg/TRzEdrndM2"><img src="https://img.shields.io/discord/1104430139275743293.svg?label=&amp;logo=discord&amp;logoColor=ffffff&amp;color=7389D8&amp;labelColor=6A7EC2&amp;style=for-the-badge" alt="" width="129" height="28" /></a>
