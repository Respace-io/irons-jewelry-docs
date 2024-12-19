---
layout: post
icon: fas fa-code
order: 3
toc: true
---
⚠️This page is Work in Progress! ⚠️ If you're looking for developmental help or want to shape the roadmap, you can join us on Discord:

<a href="https://discord.gg/TRzEdrndM2"><img src="https://img.shields.io/discord/1104430139275743293.svg?label=&amp;logo=discord&amp;logoColor=ffffff&amp;color=7389D8&amp;labelColor=6A7EC2&amp;style=for-the-badge" alt="" width="129" height="28" /></a>

## Patterns, Parts, and Materials

Patterns, Parts, and Materials are all data-registered files, under `data/<namespace>/irons_jewelry/<dir>` for your namespace and the respective `pattern`, `part`, and `material` directories.
<p></p>
### Patterns
Patterns are the blueprint for a complete piece of jewelry. Patterns can be unlocked by the player by default, or not. Unlocking a pattern requires learning from an Artisan Scroll item, which generate as loot and as villager trades.
In order for patterns you create to drop in loot or trades, you must add your pattern to the respective pattern tags. Some of those tags include:
- `#irons_jewelry:generic_lootable`
- `#irons_jewelry:high_quality_lootable`
- `#irons_jewelry:trader_sellable`
- [See all pattern tags here](https://github.com/iron431/irons-jewelry/tree/main/src/main/resources/data/irons_jewelry/tags/irons_jewelry/pattern)

Patterns are composed of part ingredients (part definitions combined with material costs) and determine the bonus a worn piece of this jewelry will provide. This is where the generic buffs are assigned, such as "this ring provides an attribute".

{% include json-root.html jsonSchema=site.data.pattern_definition %}
<p></p>
### Part Definitions
Part Definitions are the definitions for the individual components that can be used to construct a piece of jewelry. These mostly hold rendering information, but also what materials are allowed to make this part. 
{% include json-root.html jsonSchema=site.data.part_definition %}
<p></p>
### Material Definitions
Material Definitions are used to associate items with a material that can be used in jewelcrafting, as well as the bonuses it provides, and rendering information. This is where the specific bonus parameters are defined, such as "Gold gives *x* attribute, or does *y* action".
{% include json-root.html jsonSchema=site.data.material_definition %}
### Quality Scalars
Throughout many other schemas, you will see Quality Scalars. This is a number provider that scales based on the quality of a piece of jewelry. It can scale positively or negatively, such as a buff duration or cooldown time.
{% include json-root.html jsonSchema=site.data.quality_scalar_schema %}

## Registered Types

### Jewelry Types
Jewelry Types provide the association between a pattern and an item. Custom jewelry types can be registered through code.
- `irons_jewelry:ring`
- `irons_jewelry:necklace`

### Bonus Types
Bonus types are registered behaviors that execute on an input bonus parameter. Custom bonus types can be made through code.
- `irons_jewelry:piglin_neutral_bonus`
  - Utilizes `irons_jewelry:empty` parameter type
  - Makes piglins neutral to the wearer
- `irons_jewelry:attribute_bonus`
  - Utilizes [Attribute](/data-format/#bonus-parameter-types) parameter type
  - Provides an attribute modifier to the wearer
- `irons_jewelry:effect_on_hit_bonus`
  - Utilizes [Positive Effect](/data-format/#bonus-parameter-types) parameter type
  - Applies a mob effect to wearer when the wearer hits an entity
- `irons_jewelry:on_projectile_hit_bonus`
  - Utilizes [Action](/data-format/#bonus-parameter-types) parameter type
  - Executes an action when the wearer hits an entity with a projectile
- `irons_jewelry:on_attack_bonus`
  - Utilizes [Action](/data-format/#bonus-parameter-types) parameter type
  - Executes an action when the wearer attacks an entity directly
- `irons_jewelry:effect_immunity_bonus`
  - Utilizes [Negative Effect](/data-format/#bonus-parameter-types) parameter type
  - Grants immunity to a mob effect
- `irons_jewelry:on_shield_block_bonus`
  - Utilizes [Action](/data-format/#bonus-parameter-types) parameter type
  - Executes an action when the wearer blocks an attack with a shield
- `irons_jewelry:on_take_damage_bonus`
  - Utilizes [Action](/data-format/#bonus-parameter-types) parameter type
  - Executes an action when the wearer takes damage

### Bonus Parameter Types
Bonus Parameter Types are a registered type object associated with a data class. This data class is used as context for the behavior of a bonus type. The instances of these data objects live on the material definition, which are picked based on the material a jewelry is made out of. 
- `irons_jewelry:attribute` (See [Attribute Instance](/data-format/#attribute-instance) schema)
- `irons_jewelry:positive_effect` (See [EffectParameter](/data-format/#effect-parameter) schema)
- `irons_jewelry:negative_effect` (See [EffectParameter](/data-format/#effect-parameter) schema)
- `irons_jewelry:action` (See [Action Runnable](/data-format/#action-runnable) schema)

## Bonus Parameter Values
Arbitrary data objects instances that hold data for the behavior of a bonus type to act upon.
##### Attribute Instance

{% include json-root.html jsonSchema=site.data.attribute_instance_schema %}

##### Effect Parameter

{% include json-root.html jsonSchema=site.data.effect_parameter_schema %}

#### Action Runnable

{% include json-root.html jsonSchema=site.data.action_runnable_schema %}

#### Actions
Action are special buffs that, when triggered, actually *do* something. Custom Actions can be registered through code. The following actions exist by default:
- `irons_jewelry:knockback` (See [Knockback](/data-format/#knockback) schema)
- `irons_jewelry:ignite` (See [Ignite](/data-format/#ignite) schema)
- `irons_jewelry:apply_effect` (See [Apply Effect](/data-format/#apply-effect) schema)
- `irons_jewelry:apply_damage` (See [Apply Damage](/data-format/#apply-damage) schema)
- `irons_jewelry:apply_freeze` (See [Apply Freeze](/data-format/#apply-freeze) schema)
- `irons_jewelry:heal` (See [Heal](/data-format/#heal) schema)
- `irons_jewelry:explode` (See [Explode](/data-format/#explode) schema)
- `irons_jewelry:create_items` (See [Create Items](/data-format/#create-items) schema)

## Action Schemas

### Knockback

{% include json-root.html jsonSchema=site.data.knockback_action_schema %}

### Ignite

{% include json-root.html jsonSchema=site.data.ignite_action_schema %}

### Apply Effect

{% include json-root.html jsonSchema=site.data.apply_effect_action_schema %}

### Apply Damage

{% include json-root.html jsonSchema=site.data.apply_damage_action_schema %}

### Apply Freeze

{% include json-root.html jsonSchema=site.data.apply_freeze_action_schema %}

### Heal

{% include json-root.html jsonSchema=site.data.heal_action_schema %}

### Explode

{% include json-root.html jsonSchema=site.data.explode_action_schema %}

### Create Items

{% include json-root.html jsonSchema=site.data.create_items_action_schema %}

<!-- buffer for the TOC -->
<div style="height: 800px"></div>




