---
layout: post
icon: fas fa-code
order: 3
toc: true
---

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

## Registered Types

### Jewelry Types

- `irons_jewelry:ring`
- `irons_jewelry:necklace`

### Bonus Types

- `irons_jewelry:piglin_neutral_bonus`
- `irons_jewelry:attribute_bonus`
- `irons_jewelry:effect_on_hit_bonus`
- `irons_jewelry:on_projectile_hit_bonus`
- `irons_jewelry:on_attack_bonus`
- `irons_jewelry:effect_immunity_bonus`
- `irons_jewelry:on_shield_block_bonus`
- `irons_jewelry:on_take_damage_bonus`

### Bonus Parameter Types

- `irons_jewelry:attribute` -> [Attribute Instance](/data-format/#attribute-instance)
- `irons_jewelry:positive_effect` -> [EffectParameter](/data-format/#effect-parameter)
- `irons_jewelry:negative_effect` -> [EffectParameter](/data-format/#effect-parameter)
- `irons_jewelry:action` -> [Action Runnable](/data-format/#action-runnable)

## Bonus Parameter Values

##### Attribute Instance

{% include json-root.html jsonSchema=site.data.attribute_instance_schema %}

##### Effect Parameter

{% include json-root.html jsonSchema=site.data.effect_parameter_schema %}

#### Action Runnable

{% include json-root.html jsonSchema=site.data.action_runnable_schema %}

#### Actions

- `irons_jewelry:knockback` -> [Knockback](/data-format/#knockback)
- `irons_jewelry:ignite` -> [Ignite](/data-format/#ignite)
- `irons_jewelry:apply_effect` -> [Apply Effect](/data-format/#apply-effect)
- `irons_jewelry:apply_damage` -> [Apply Damage](/data-format/#apply-damage)
- `irons_jewelry:apply_freeze` -> [Apply Freeze](/data-format/#apply-freeze)
- `irons_jewelry:heal` -> [Heal](/data-format/#heal)
- `irons_jewelry:explode` -> [Explode](/data-format/#explode)
- `irons_jewelry:create_items` -> [Create Items](/data-format/#create-items)

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




