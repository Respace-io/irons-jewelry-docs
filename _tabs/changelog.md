---
layout: post
icon: fa-solid fa-list-ul
order: 12
toc: true
---
<style>
.yellow {
color:rgba(255, 194, 41, 0.5);
}
</style>

<hr>

## <span class="yellow"> [3.8.4] (1.21) 2024-10-31</span>
### Fixes
- Fixed Knockback CME exception

## <span class="yellow"> [3.8.3] (1.21) 2024-10-30</span>
### Additions
- Spellbooks and other books can now be placed in chiselled bookshelves

### Changes
- Removed Caelus as a dependency

### Fixes
- Optimize Knockback handler
- Optimize Guiding Bolt Manager
- Fixed Guiding Bolt Effect not homing if you shoot a projectile from inside the mob's hitbox range
- Fixed dangerous ordering of portal frame saving
- Fixed Patchouli book recipe

## <span class="yellow"> [3.8.2] (1.21) 2024-10-22</span>
### Changes
- Reimplement Patchouli Compat for 1.21+

### Fixes
- Add config safety check to jei plugin
- Temporarily remove apothic attributes compat to restore cross version compatibility

## <span class="yellow"> [3.8.1] (1.21) 2024-10-21</span>
### Fixes
- Fixed dedicated server startup issue

## <span class="yellow"> [3.8.0] (1.21) 2024-10-21</span>
### Additions
- Added Item Component for Casting Implement Functionality
  - irons_spellbooks:casting_implement
- Added Item Component for Multihand Weapon Functionality
  - irons_spellbooks:multihand_weapon
- Added Config to disable Scroll Upgrading, courtesy of Cephelo
- Added Mana Regeneration Multiplier Config
- Added Casting Movement Speed Attribute
  - Affects the user's movement speed while casting
  - Currently Unused
- Added Apothic Attributes Formatting Compatibility
- Expanded Lectern Functionality
  - Spellbooks can now be placed on lecterns
  - "Lore Items" can now be placed on lecterns
- Added Archevoker Logbook item
  - Has translated and untranslated variants
  - Spawns in Evoker Fort tower lectern
  - Replaces Written Book in Villager Bible Questline

### Changes
- Updated Languages
  - Russian, thanks to Tefny and Quark
  - Added Vietnamese support, thanks to Le P. Thanh Sang
- Root no longer affects any boss (instead of just Ender Dragon)
- Black hole is now less effective against bosses, as well as creatures with high knockback resistance

### Fixes
- Void Tentacles are no longer affected by Black Hole
- Fixed Pedestal being unable to sync empty item stacks
- Fixed Staffs always showing imbued item's cooldown reduction
- Fixed Energy Swirl effect incorrectly calculating model transforms
- Fixed Aoe Entities being affected by explosion knockback
- Fixed Inscription Table Exploit

### API
- Added Events, courtesy of clement
  - CounterSpellEvent
  - SpellSummonEvent
- Multihand and Casting Implement functionality is now component based. Nothing needs to be done if you were not manually implementing these

## <span class="yellow"> [3.4.0.3] (1.20.1) 2024-10-21</span>
### Additions
- Config to disable scroll upgrading
### Fixes 
- Backported Fixes
  - Inscription Table Exploit
  - Water Processor
  - AOE knockback
  - Energy Swirl Rendering


## <span class="yellow"> [3.7.0] (1.21) 2024-09-28</span>
### Additions
- Added new Advancement: A Fool's Foley
  - Anger a wizard by looting a nearby chest
- Added config for Hoglins to pass on Netherward Tincture's effect when bred (defaulted to true)
- Added Waterlogging to Inscription Table, Scroll Forge, Firefly Jar, Armor Pile, and Pedestal

### Fixes
- Fixed advancements not being visible due to 1.21 format change
- Fixed blood cauldron block crashbug due to missing default interaction
- Fixed poison cancelling long casts
- Fixed Alchemist Cauldron and hopper interaction

## <span class="yellow"> [3.4.0.2] (1.20.1) 2024-09-28</span>
### Fixes 
- Backported Fixes
  - Fixed Alchemist Cauldron and hopper interaction

## <span class="yellow"> [3.4.0.1] (1.20.1) 2024-09-18</span>
### Changes
- Backported Spell Balance changes from 3.6.0 and 3.5.0
- Backported Necromancer nerf from 3.4.5

### Fixes
- Backported various fixes
  - Fixed Flaming Strike Spell being able to damage items
  - Fixed Scorch Spell entity recast positioning
  - Fixed some spells not using config power multiplier
  - Fixed Affinity Rings being able to roll disabled spells
  - Fixed Chain Lightning entity using a dangerous comparator
  - Fixed Priest dangerous level lookup during spawn
  - Fixed casting mobs dangerous server operation during load from nbt

## <span class="yellow"> [3.6.2] (1.21) 2024-09-17</span>
### Fixes
- Fixed generated resources being omitted from last build

## <span class="yellow"> [3.6.1] (1.21) 2024-09-15</span>
### Changes
- Wither effect can now be cleansed


## <span class="yellow"> [3.6.0] (1.21) 2024-09-15</span>
### Additions
- Added Cleanse Spell
- Added Ice Spikes Spell

### Changes
- Necromancers now only drop Scrolls on player kill
- Spell Balance Changes:
  - Guiding Bolt
    - Guiding Bolt Projectile Speed increased by 30%
    - Guided Effect duration increased from 15s -> 25s
    - Guided Projectiles home from farther, and more quickly
    - These changes should make hitting the Guiding Bolt debuff more rewarding and worthwhile
  - Fortify
    - Decreased cast range from 16 -> 8 blocks
  - Sunbeam
    - Increased base damage from 10 -> 12
    - Increased damage per level from 1 -> 1.5
    - Decreased windup time from 20 -> 15 ticks
    - These changes should make Sunbeam more viable compared to other pillar aoe spells
  - Heal (Requires Config Reset)
    - Base Healing reduced from 6 -> 5 HP
    - Max Level reduced from 10 -> 8
    - Min Rarity increased from common -> uncommon
    - Cooldown increased from 25s -> 30s
    - Mana Cost per level increased from 10 -> 15
    - While Heal was intended to be a jack-of-all-trades, Heal always outperformed and overshadowed other healing spells in their own niche. These changes should make relying on just Heal without specing holy power less universally viable
  - Blessing of Life
    - Base healing increased from 4 -> 6 HP
  - Healing Circle
    - Increased radius from 4 -> 5 blocks
  - Divine Smite
    - Improved damage hitbox placement
    - Increased damage hitbox radius
    - Increased base damage from 5 -> 8
  - Flaming Strike
    - Improved damage hitbox placement and hit registration
    - Decreased damage per level from 3 -> 2
    - Redid Spell Icon

### Fixes
- Fixed Healing Circle Entity Effect Particles
- Fixed Flaming Strike Spell being able to damage items
- Fixed Scorch Spell entity recast positioning
- Fixed some spells not using config power multiplier
- Fixed entity tags not being loaded
- Fixed missing tool/enchantment tags for various items

## <span class="yellow"> [3.5.0] (1.21) 2024-09-03</span>
### Additions
- Added Portal Frame block, allowing for permanent portal spell connections
- Added King's Lullaby music disc (Music by Caner Crebes)
- Added Sunbeam Spell
- Added decorated pots to various Catacombs rooms
- Added decorated pot room to Pyromancer Tower cellar

### Changes
- Spell Balance Changes:
  - Acid Spit:
    - Remove spell power scaling of rend percent
    - Increased base rend percent (5%->20%)
    - Increased base effect duration (15s->20s)
  - Heat Surge:
    - Removed spell power scaling of rend percent
    - Decreased default rend percent (20% -> 15%)
  - Blight:
    - Removed spell power scaling from effect percents
  - Teleport, Blood Step, Frost Step:
    - Teleport range now scales with a softcap
- Aoe Fields now fit to the ground better
- Overhauled Ancient Battlegrounds origin structure piece
- Separated Fire Particle from Fire Emitter Particle, and now use fire particle is various contexts

### Fixes
- Fixed Priest's Villager Bible trade
- Fixed Scrolls without spell container component crashing the client
- Fixed Armor Cape Layer not tracking to entity's during various animations
- Fixed Affinity Rings being able to roll disabled spells
- Fixed geckolib mob invisibility handling

## <span class="yellow"> [3.4.5] (1.21) 2024-08-24</span>
### Additions
- Added Amulet of Teleportation

### Changes
- Nerfed Necromancer's spell power

### Fixes
- Fixed Necromancers not spawning naturally
- Fixed anger particles playing when they shouldn't for neutral casting mobs
- Fixed Rod o' Lightning no longer being fire resistant
- Fixed holding on to references of various objects, causing additional memory consumption
- Fixed Chain Lightning entity using a dangerous comparator
- Fixed Priest dangerous level lookup during spawn
- Fixed casting mobs dangerous server operation during load from nbt
- Fixed SyncedSpellData copying all data on death, instead of only persistent data
- Fixed duplicate curio attribute modifier ids

## <span class="yellow"> [3.4.4] (1.21) 2024-08-11</span>
### Changes
- Remove InterModComms with curios to fix compat with a different curios API port that broke inter mod comms

## <span class="yellow"> [3.4.3] (1.21) 2024-08-10</span>
### Fixes
- Fixed default magic data attachment having null server player

## <span class="yellow"> [3.4.0] (1.19.2 | 1.20.1) 2024-08-10</span>

### Additions
- Added Weapon Parts, crafted from Arcane Salvage and used for crafting magic weapons
- Added Spellbreaker, a craftable imbued sword
- Added Amethyst Rapier, a craftable imbued sword

### Changes
- Arcane Anvil now returns Upgrade Orbs when using a Shriving Stone
- Reworked Alchemist Cauldron
  - Water Level and Liquid Contents are no longer separate values. This should make interactions much more intuitive
- Loot-Only curios can now be recycled
  - Can be Smelted into Arcane Salvage, and crafted from Arcane Salvage and a designated item
- Affinity Rings can now be attuned to specific spells by combining a ring with a scroll of any level in the Arcane Anvil

### Fixes
- Fixed Firefly Jar not having a loot table
- Fixed True Invisibility not affecting the aggro of mobs that use Brain for targeting
- Fixed Inscription Table ghost block/dupe when exploded
- Fixed Abyssal Shroud destination logic
- Fixed Inscription Table bug/exploit relating to death

## <span class="yellow"> [3.4.2] (1.21) 2024-08-10</span>
### Changes
- Adjusted drop rate of magic items Trial Chambers chests

### Fixes
- Fixed null crash when rendering armor with enchantment glint or smithing trims
- Fixed Arcane Anvil not saving imbued spell containers

## <span class="yellow"> [3.4.1] (1.21) 2024-08-09</span>
### Fixes
- Added missing common item/block tags for Mithril
- Fixed Firefly jar recipe using wrong glass tag
- Fixed loot tables being allowed to roll mace enchantments
- Fixed dedicated server crash

## <span class="yellow"> [3.4.0] (1.21) 2024-08-09</span>

### Additions
- Port to 1.21
- Added crouch display to Alchemist Cauldron contents
- Added specific Stronghold/End City loot tables for magic items
- Added Loot to Trial Chambers
  - Pots
    - Chance to drop Arcane Essence, or rarely drop a Scroll 
  - Chests
    - Arcane Essence, Cloth, Scrolls, Blank Runes, Curios, Ink, and Elixirs
  - Spawners
    - Mana Potions
  - Ominous Spawners
    - High Quality Mana Potions, and Elixirs
  - Vaults
    - Scrolls, Ink, Curios, Arcane Essence, and Blank Runes
  - Ominous Vaults
    - Magic Equipment, High Tier Resources, Empty Upgrade Orbs, High Quality Scrolls/Ink, and Arcane Essence
- Added Mithril
  - Mithril Ingot
  - Mithril Scrap
  - Raw Mithril
  - Mithril Ore
  - Deepslate Mithril Ore
- Added Weapon Parts, crafted from Mithril and used for crafting magic weapons
- Added Spellbreaker, a craftable imbued sword
- Added Amethyst Rapier, a craftable imbued sword
- Added Autoloader Crossbow, a unique Trial Chambers reward
- Added Ring of Expulsion, a unique Trial Chambers reward
- Added Ring of Visibility, a unique Trial Chambers reward

### Changes
- Affinity Data can now specify a bonus greater than 1
- Arcane Anvil now returns Upgrade Orbs when using a Shriving Stone
- Reworked Alchemist Cauldron
  - Water Level and Liquid Contents are no longer separate values. This should make interactions much more intuitive
- Loot-Only curios can now be recycled
  - Can be Smelted into Mithril Scrap, and crafted from Mithril Scrap and a designated item
- Affinity Rings can now be attuned to specific spells by combining a ring with a scroll of any level in the Arcane Anvil
- Pyromancer Chestplate now has a cape addition
- Casting Mobs now display capes from armor with capes

### Fixes
- Fixed Firefly Jar not having a loot table
- Fixed True Invisibility not affecting the aggro of mobs that use Brain for targeting
- Fixed Inscription Table ghost block/dupe when exploded
- Fixed Abyssal Shroud destination logic
- Fixed Inscription Table bug/exploit relating to death

### API
- Removed irsonspellbooks from java group id
  - io.redspace.ironsspellbooks.irons_spellbooks => io.redspace.irons_spellbooks
- Removed Deprecated Content
  - CastType#holdToCast
  - AbstractSpell#needsLearning (replaced by AbstractSpell#requiresLearning)
  - AbstractEldritchSpell class
- Added Events
  - AlchemistCauldronBuildInteractionsEvent

## <span class="yellow"> [3.3.0] (1.19.2 | 1.20.1) 2024-07-16</span>
### Changes
- Large Balance Changes
  - Armor
    - School Armor now gives +10% school spell power per piece (previously +8%)
    - School Armor and Netherite Battlemage Armor now gives +5% Spell Power per piece
    - School Armor and Netherite Battlemage Armor now gives +125 Max Mana (previously +100)
    - Scarecrow Armor now gives +75 Max Mana (previously +50)
  - Scrolls
    - Increased stack size to 64
    - Upgrading scrolls now requires one ink per level, instead of a scroll of equal level
      - The rarity of the ink is equal to the rarity of the resulting scroll rarity
  - Upgrade Orbs
    - Spell Power Upgrade Orbs now give +5% power (previously +3%)
    - Cooldown and Resistance Upgrade Orbs now give +5% Cooldown/Spell Resistance (Previously +6%)
  - Spellbooks
    - Spellbooks now give max mana
      - "High Tier" spellbooks (spellbooks with spell power buffs) now give +200 Max Mana
      - Enchanted Spell Book and Ruined Spell Book now gives +100 Max Mana
      - Apprentice Spell Book now gives +50 Max Mana
- Tweaked Alchemist Cauldron Texture
- Removed strict hold-to-cast mechanics from scrolls and casting implements
- Adjusted Cone of Cold particles

### Fixes
- Fixed JEI Scroll Upgrade recipes showing one additional level past max level
- Fixed Long Casts going on cooldown if the cast was cancelled by opening a menu
- Fixed the Dead King dropping a loot table of ink, instead of always Legendary Ink
- Fixed ground height algorithm used in Target Area rendering
- Fixed spell rarity of a spell over its max level appearing as common

## <span class="yellow"> [3.2.2] (1.19.2 | 1.20.1) 2024-07-09</span>
### API
- Abstracted AbstractCastingMob into IMagicEntity interface

## <span class="yellow"> [3.2.1] (1.19.2 | 1.20.1) 2024-07-05</span>
### Changes
- Updated Japanese Translations, thanks to SAGA
- Updated Korean Translations, thanks to smoong
- Updated Russian Translations, thanks to Tefnya

### Fixes
- Fixed world upgrader code resetting spellbook slot NBT on relog after using Spell Slot Improvement item
- Fixed visual bug with the cast command resetting an item's use progress
- Fixed config loading incompatibility with Modernfix
- Fixed Arcane Anvil JEI recipe memory usage

## <span class="yellow"> [3.2.0] (1.19.2 | 1.20.1) 2024-06-19</span>
### Additions
- Added Flaming Barrage Spell
- Added Ball Lightning Spell
- Added Sacrifice Spell
- Added Rod o' Lightning, a staff enhancing lightning magic
- Added Energized Core, a crafting ingredient to the Rod o' Lightning
- Added Lesser Spell Slot Improvement, an item that can increase a Spell Book's capacity up to 12 slots
- Added Mana Text offsets in client config
- Added server config option to disable spellcasting in adventure mode

### Changes
- Buffed Scorch Spell
  - Increased radius
  - Now leaves a fiery field where it scorches
- Made Thunderstorm targeting more strict to lessen collateral damage
- Restricted the damage types (mainly damage over time) that can trigger an Echoing Strike
- Updated Heat Surge and Frostwave spell particles
- Updated various language files thanks to community members
- Slight adjustment to Priest AI

### Fixes
- Fixed Portals not playing the destination sound to the player teleporting
- Fixed Capes and Angel Wings rendering over each other
- Fixed Neutral Trading Wizards ceasing to trade after taking damage from a non-player source
- Fixed certain magic summons being attack unprovoked by mobs like Iron Golems

## <span class="yellow"> [3.1.7.1] (1.20.1) 2024-05-29</span>
# Fixes
- Fixed casting mobs no longer displaying long cast animations

## <span class="yellow"> [3.1.7] (1.19.2 | 1.20.1) 2024-05-28</span>
### Additions
- Added config for disabling Wandering Trader magic item trades (default is enabled)

### Changes
- While using the Cast command, if the executing entity could not support long casts, they now skip the cast time in order to successfully cast the spell
- Adjusted Cone of Cold particles

### Fixes
- Fixed Netherite Battlemage armor not being fire resistant
- Fixed Black Hole Spell's order in creative menu/JEI
- Fixed Spellcasting mobs casting Fang Ward while out of range
- Fixed disabling all spells to cause merchant trying to sell scrolls to crash the client
- Fixed Ice Block Projectile serialization
- Fixed Scroll exploit

### API
- Improved functionality of SpellSelectionManager.SpellSelectionEvent. Still a work in progress
- Removed Deprecated Methods/Events
  - SpellCastEvent (Previously Replaced by SpellPreCastEvent and SpellOnCastEvent)
  - SpellSelectionManager#initOther
  - AbstractSpell#getLevel(int, LivingEntity) (Previously replaced by getLevelFor(int, LivingEntity))
  - AbstractSpell#getMana(int, LivingEntity) (Previously replace by getMana(int))
  - AbstractSpell#onCast(Level, int, LivingEntity, MagicData) (Previously replace by onCast(Level, int, LivingEntity, CastSource, MagicData))
  - Utils#doMeleeAttack (Previously replaced by doMeleeAttack(Mob, Entity, DamageSource))

## <span class="yellow"> [3.1.6] (1.19.2 | 1.20.1) 2024-05-20</span>
# Additions
- Added Italian and Chinese-Taiwan localizations

# Fixes
- (1.19.2 only): Fixed old structures relying on outdated catacombs file preventing their extensions from generating

## <span class="yellow"> [3.1.5] (1.19.2 | 1.20.1) 2024-05-13</span>
### Additions
- Added Scorch Spell
- Added Echoing Strikes Spell
- Added Thunderstorm Spell
- Added several new Catacombs room pieces
- Added client config for disabling boss music
- Added new command parameter to mana command: "get"

### Changes
- Adjusted Wall of Fire spell icon to be differentiable from Scorch spell icon

### Fixes
- Fixed Dead King Music potentially playing twice over if killed and respawned near the Dead King fight
- Improved Abyssal Shroud teleporting mechanics potentially making the player become stuck
- Fixed the Blood Staff not renaming properly when upgraded
- Fixed mana regeneration of less than one being truncated
- Fixed spellbook curio render logic affecting custom body models

### API
- AnimationHolder now allows non-irons_spellbooks namespaces for animation resourcelocations

## <span class="yellow"> [3.1.4] (1.19.2 | 1.20.1) 2024-04-26</span>
### Additions
- Added AllowCrafting config to each spell, which can prevent a spell from being craftable in the scroll forge (PR of squoshi)

### Changes
- Reworked Various Spell Icons, thanks to Renovated Studios
  - Frostwave
  - Sculk Tentacles
  - Telekinesis
  - Spider Aspect
  - Summon Ender Chest
  - Shockwave
  - Charge
  - Dragon's Breath
  - Poison Arrow
  - Poison Splash
  - Summon Horse
- Adjusted Colors of various spell icons to be more consistent
- Changed GUI arrangement of staff models to better fit one slot
- Reverted Scarecrow Helmet to old texture

### Fixes
- Fixed Ancient Knight's arms no longer animating on 1.19.2
- Fixed Apothecarist ears no longer animating
- Fixed spell level buffs applying inconsistently

### API
- Added UpdateClient helper class to API package (PR from IGN-Styly)
- Added ModifySpellLevelEvent, allowing modders to create custom buffs that affect a spell's level, like affinity rings

## <span class="yellow"> [3.1.3] (1.19.2 | 1.20.1) 2024-04-06</span>
### Fixes
- Fixed new SpellOnCastEvent returning the wrong level

## <span class="yellow"> [3.1.2] (1.19.2 | 1.20.1) 2024-04-05</span>
### Additions
- Added Eldritch Spell Power and Resistance attributes (not utilized in game yet)

### Changes
- Increased the caps on most attributes. Mana regen can now be 0, but not negative

### Fixes
- Fixed Casting Mob model overrides messing with the Dead King's new melee animation
- Fixed client data persisting after logout (such as the spell bar)
- Fixed left-clicking while the spell wheel is open to grab the screen without closing the menu
- Fixed Quick Casts only being able to cast from player's spell book instead of all their spells

### API
- Moved the SpellSelectionManager into the API package (may be a breaking change for mods relying on more than the API)
- Added SpellSelectionManager.SpellSelectionEvent for modders to add custom spell sources to the player
- Split the SpellCastEvent into SpellPreCastEvent and SpellOnCastEvent

## <span class="yellow"> [3.1.1] (1.19.2 | 1.20.1) 2024-03-23</span>
### Additions
- Added item tag support to imbue/upgrade whitelist/blacklist

### Changes
- Adjusted Heat Surge, Flaming Strike, and Magic Missile spell icons
- Reformatted Gust Spell's tooltip
- Adjusted when an item is explicitly labeled as imbeuable

### Fixes
- Fixed non-spellbook Apotheosis gems requiring Apothic curios to register
- Fixed neutral spellcasting mobs still not trading with players after no longer being angry
- Fixed generic Spell Resist attribute not applying to spell damage

## <span class="yellow"> [3.1.0] (1.19.2 | 1.20.1) 2024-03-17</span>
### Additions
- (1.20.1): Fully ported Tetra compatibility
- Added Shockwave Spell
- Added Pyromancer Tower Structure
  - Pyromancer now lives here instead of the Mangrove Hut structure
  - Added Fire Ale item
- Added the Apothecarist, Nature spellcasting mob
  - Has taken over and refurbished the Mangrove Hut structure
  - Neutral, and will trade with the player
  - Uses Splash Potions in tandem with spells
  - Added Netherward Tincture item, which can only be obtained by trading with the Apothecarist
- Added Boss Music to the Dead King boss fight, courtesy of Caner Crebes
- Added Hogskin -> Leather recipe
- Added blastwave particle to Starfall Comets

### Changes
- Pyromancer Rework
  - Now Neutral
  - Can be traded with
  - Now Spawns in Pyromancer Tower instead of Mangrove Hut
- Dying entities can no longer be targeted by spells
- Reworked Spell Griefing Mechanics
  - Instead of using mobGriefing gamerule, there is now a spellGriefing server config
  - The default is off (no spell griefing)
- Reworked Fireball Spell
  - Now has 5 levels (requires config reset)
  - Minimum rarity is now rare (requires config reset)
  - Explosion radius is larger at lower levels
  - Damage is lower at higher levels
  - Reworked explosion visuals
  - Now requires spellGriefing to be enabled to break and ignite blocks
- Adjusted various ring textures
- Reworked Catacombs Throne Room
- Reworked Dead King melee animations
- Dead King Balance Changes
  - Decreased projectile resistance from 25%->0%
  - Increased based health by 25%
  - Now immune to lava
  - Now immune to fall damage
- Reworked all Casting Mobs' look control for better vertical spell casting

### Fixes
- Fixed Spell Bar configured Y offset applying to X and Y
- Fixed Dead King's legs improperly animating during phase transition animation
- Fixed Zap Particle rendering at many rotations
- Fixed Shriving Stones being able to remove the spells of unique items (Hither-Thither wand)
- Fixed client crash on the inscription table caused by JEI resetting the spellbook slot
- Fixed Arrow Volley entity not having an owner
- Fixed Evoker Fort cages having a gap, which pillagers could shoot and kill captive villagers through
- Fixed Apotheosis gem values
- Fixed scrolls with a count of more than 1 not displaying their school texture

### API
- Added interface for easier use of ExtendedArmorMaterials

## <span class="yellow"> [3.0.1] (1.19.2 | 1.20.1) 2024-02-28</span>
### Additions
- Added JEI support to Upgrade Orb recipes

### Changes
- Redid Magma Bomb spell icon
- Staffs can now be upgraded

### Fixes
- Fixed teleportation clipping issues caused by previous update
- Fixed incorrect loot function type cast
- Fixed Projectiles not being able to go through portals
- Fixed client crash caused by upgrading curio items on a dedicated server
- Fixed mismatched Russian translations between versions
- Fixed tooltip index operation potentially being out of bounds with other mod's editing the tooltip at the same time
- Fixed Arrow Volley spell's sub-arrows not keeping track of the original caster

## <span class="yellow">Curio Casting [3.0.0] (1.19.2 | 1.20.1) 2024-02-27</span>
### Additions
- Added Curio Casting System
  - Added Curio slot for spell books
  - Added keybind to cast active spell from your spell book
  - Removed ability to cast by right-clicking with a spell book
  - Removed Rarity limit on Spell Books
  - Increased all Spell Books' spell slot count
  - Unique Spell Books now have additional unlocked slots
  - Added Casting Implements, which allow right-clicking to cast active spell
  - Reworked imbued items (see changes)
- Added Casting Implements
  - Can be right-clicked to cast your active spell
  - Offer spellcasting attributes when held in either hand
- Added Staves (a type of Casting Implement)
  - Graybeard Staff
  - Artificer's Cane
  - Ice Staff
  - Blood Staff (No longer a spell book, see Necronomicon)
- Added Netherite Battlemage armorset
  - Protection of Netherite armor without knockback resistance
  - Mana bonus of School armor without spell power
- Added functionality for Curio Items to be upgraded with upgrade orbs
- Added Recastable Spells
  - Once being cast, they have an additional time window to cast again, for a repeated or separate effect, allowing for multi-stage spells
  - Mana is only consumed on the first cast, and the cooldown triggers after all recasts are expended or wear out
- New Spells
  - Portal Spell (recastable)
  - Eldritch Blast Spell (recastable)
  - Stomp Spell
  - Gluttony Spell
  - Flaming Strike Spell
- Added the Necronomicon
  - Unique Spell Book drop from the Dead King
  - Comes with Blood Slash (5), Blood Step (5), Ray of Siphoning (5), and Blaze Storm (5)
  - Comes with affinity for Raise Dead (+1 level to Raise Dead)
- Cast Command
  - Basic functionality for now
- Added clearCooldown command
- Added Impaled Icebreaker Ship structure
  - Found very rarely in frozen biomes
  - Contains the key crafting component of the Ice Staff
  - Locator maps to this structure can be found in the Mountain Tower
- Added more client configs regarding HUD elements
- Added Hither Thither Wand
  - Unique item, comes imbued with Portal Spell
  - Rare trade of Wandering Traders
- Added 3d Spell Book Models for each spell book, thanks to Cakeman

### Changes
- Spell Book can no longer be right-clicked to cast (See Additions for curio casting system)
- Reworked Spells:
  - Wall of Fire now uses recasting to stage each anchor point before creating the wall
  - Burning Dash now provides I-frames and damages mobs you pass through instead of only where you launch from
  - Spectral Hammer QOL: must be cast on a block it can mine to initiate, can mine many more block types, no longer leaves debris, has a longer range, and much shorter cooldown
- Reworked Imbued Items
  - Armor and Curios now support imbuements
    - Tarnished Crown can now be imbued
    - Chestplate of School armor and Netherite Battlemage armor can now be imbued
  - Imbued items support multiple spells on one item (not yet used in gameplay)
  - Imbued items now add their spells into the player's spell wheel
  - Imbued items can no longer be right-clicked to cast their spell, instead integrating with the curio casting system and its keybinds
- Reworked Arcane Anvil recipe to no longer require Netherite (with accompanying texture change)
- Reworked Spell Book Progression
  - Removed Rarity limit on Spell Books
  - Increased all Spell Books' spell slot count
  - Unique Spell Books now have additional unlocked slots
- Reworked Scroll Textures (Thanks to Bodya33381 for textures)
  - Each school now has a scroll texture
- Reworked Apotheosis Compatibility
  - Added and tweaked many affixes for armor, weapons, and curios
  - Affixes for Spell Books now require Apothic Curios to work
- Adjusted various spell icons
- Changed default keybind Spell Wheel Scroll Modifier (LShift->LAlt)
- Reworked Mountain Tower interior layout
- Items no longer visually bob while on Pedestal block
- The Dead King is now guaranteed to drop either the Blood Staff or Necronomicon (only one)
- Wandering Trader can now sell ink
- Reworked Advancement tree
- Reworked Apotheosis Affixes
### Fixes
- Various changes and fixes

### API
- Various breaking changes

## <span class="yellow">[2.2.2] (1.19.2 | 1.20.1) 2024-01-26</span>
### Additions
- Added a config for better creeper thunderhit behavior

### Changes
- Magic projectiles and lightning can no longer hit their caster
- Made the Keeper Flamberge item fire resistant
- Reworked Lightning Bolt spell hit detection
- Spectral hammer no longer has a chance to leave blocks behind, falling blocks are now visual only
- Redid the Pyromancer and Electromancer Hat icons

### Fixes
- Fixed exploit involving Spectral Hammer spell
- Fixed Spectral Hammer stack overflow at massive sizes
- Affinity Rings can no longer generate for spells with only one level (such as Summon Ender Chest)

## <span class="yellow">[2.2.1] (1.19.2 | 1.20.1) 2024-01-09</span>
### Changes
- Optimized GuidingBoltManager
- Optimized LivingSpawnEvent

### Fixes
- Fixed GuidingBoltManager raycasting into unloaded chunks

## <span class="yellow">[2.2.0] (1.19.2 | 1.20.1) 2024-01-02</span>
### Additions
- Spells
  - Added Haste Spell
  - Added Slow Spell
  - Added Heat Surge Spell
  - Added Frostwave Spell
  - Added Arrow Volley Spell
  - Added Recall Spell
- Added Furled Map Item, an NBT-driven holder for a locator map
- Added Trades to the Priest
  - Furled Map to Evoker Fort
  - Buys and Sells health potions
  - Buys special item for the Villager Bible
- Added Taiga Priest House Variant
- Added two new Evoker Fort camp half pieces
  - Gallows
  - Campsite
- Added a recipe to convert inscribed runes back into Blank Runes
- Added a recipe to convert frozen bones into bone meal

### Changes
- Neutral Wizards now have anger levels, where actions can make them angry but not aggressive.
- Neutral Wizards will now be angered by players opening their chests
- The Priest now has a nosepiece to go with his mask
- Priest Hood has been renamed to Priest Mask to reflect the texture change
- Reworked Guiding Bolt's Guided Effect mechanic. It is now much smoother and more consistent.
- Reworked the "questline" to obtain the Villager Bible
  - Nitwits no longer spawn in Evoker Forts, nor have trades
  - The final trade is done with the Priest
- Evoker Forts are now more rare
- Improved Wizard fleeing behavior (they will cast backwards less often)
- Adjusted Cone of Cold's particles
- Made the Mountain Tower structure less common
- Blazes are now vulnerable to Ice magic
- Divine Smite will now also apply additional enchantment effects, such as fire aspect
- Improved several mob effect icons
- Improved Heal Spell icon
- Improved several spell icon's, courtesy of Renovated Studios
  - Black Hole
  - Blood Slash
  - Devour
  - Magic Arrow
  - Poison Arrow
  - Poison Breath
  - Fire Breath
  - Ray of Siphoning
  - Ray of Frost
  - Sonic Boom
  - Starfall
  - Wall of Fire

### Fixes
- Fixed Divine Smite being able to damage Items
- Fixed Blood Slash's radius calculations
- Fixed Lightning Bolt Spell's aerial targeting
- Fixed successfully using a bottle on a creeper to obtain Bottle o' Lightning still causing the offhand to perform an action
- Fixed Ray of Frost not taking an entity's base freeze time into account when applying freeze
- Fixed Firecracker Spell's incredibly inconsistent damage
- Fixed Cooldowns not persisting serverside after death/player clone

## <span class="yellow">[2.1.2] (1.19.2 | 1.20.1) 2023-12-12</span>
### Changes
- Telekinesis
  - Telekinesis base range increased
  - Telekinesis mana cost no longer scales with level
  - Telekinesis duration now scales with level
  - Telekinesis force is now smoother
- Dragonskin dropped from Ender Dragons now floats and glows

### Fixes
- Fixed Spell MobEffects persisting after death
- Fixed Summoned Entities with no summoner causing a crash after killing a player
- Fixed /kill not working on Dead King Corpse entity

## <span class="yellow">[2.1.1.1] (1.20.1) 2023-12-07</span>
### Changes
- Updated minimum Geckolib version to 4.3.1

## <span class="yellow">[2.1.1] (1.19.2 | 1.20.1) 2023-11-28</span>
### Fixes
- Fixed compatibility with mods attempting to access spell names from the server
- (1.20.1) Fixed item cooldown rendering using the wrong coordinate
 
## <span class="yellow">Eldritch Update [2.1.0] (1.19.2 | 1.20.1) 2023-11-26</span>
### Additions
- Added New School, Eldritch
  - Spells
    - Added Planar Sight Spell
    - Added Sonic Boom Spell
    - Added Telekinesis Spell
    - Reenabled Abyssal Shroud Spell
    - Reworked Sculk Tentacles Spell (was Void Tentacles)
  - Items
    - Added Eldritch Manuscript Item
    - Added Ancient Knowledge Fragment Item
  - Research System
    - Eldritch Spells are unlearned by default. (Cannot be crafted nor cast)
    - Added Research Menu, accessed by Eldritch Manuscripts
- Misc
  - Added Divine Smite Spell
    - This spell is always uninterruptible
  - Added additional Wandering Trader trades
    - Sell ink to Wandering Trader
    - Buy Curios from Wandering Trader
    - Buy scrolls from Wandering Trader
    - Buy mystery bags of scrolls from Wandering Trader
    - Buy Ancient Knowledge Fragments from Wandering Trader
  - Added a Patchouli page for Schools
  - Added a learnSpell command
  - Added Ukrainian Translations
  - Added inherent mob spell resistance
    - Undead are weak to Holy magic and resistant to Blood magic
    - Fire mobs are resistant to Fire magic
    - Water mobs are weak to Lightning magic
  - Added Scroll Bar to Scroll Forge

### Changes
- Spell Balance
  - Ice Block Spell now moves faster and initiates its fall sooner
  - Counterspell Default cooldown reduced from 15s -> 10s (existing worlds need config reset)
  - Improved Lightningbolt Spell's hit detection/placement
  - Increased Lightning Lance Spell's Damage
  - Decreased Lightning Lance Spell's Default Rarity from Rare -> Uncommon (existing worlds need config reset)
  - Magma Bomb impact damage no longer scales with spell level
  - Magma Bomb aoe damage slightly increased
  - Magma Bomb radius is reduced, and now scales with spell power
  - Gust Spell is less affected by knockback resistance
- Misc
  - Unique Spell Books can have their spells improved in the Arcane Anvil, by combining it with a higher level scroll
  - Evoker Spell Book now gives +10% Evocation Spell Power
  - Improved animation smoothing
  - Updated Chinese Translations

### Fixes
- Fixed Spell Power and Resistance Attributes not being able to go below 1
- Fixed Fireward Ring strange behavior due to reliance on mob effect

### API
- Spells now have methods for crafting criteria, craftability, lootability, and interruptibility
- Consolidated mana and cooldown checks into a CastResult class
- Added canBeCastBy (returns CastResult) method to AbstractSpell

## <span class="yellow">[2.0.3] (1.19.2 | 1.20.1) 2023-10-29</span>
### Fixes
- Removed accidently left-in testing code that could mess with mana

## <span class="yellow">[2.0.2] (1.19.2 | 1.20.1) 2023-10-28</span>
### Additions
- Added Mana Regen attribute
- Added the Amethyst Resonance Charm, a craftable necklace that gives +15% mana regeneration

### Changes
- Buff Magic Arrow's base damage by 5
- Add CastSource to SpellCastEvent for developers
- Rework Priest Armor Texture, courtesy of Crydigo
- Tweak most jewelry textures
- Any armor can now be upgraded instead of only mage armor (can_be_upgraded tag has been removed)
- Spectral Hammer debris reduced

### Fixes
- Fixed inconsistent Magic Arrow block penetration
- Fixed the two-handed sword models when using left hand mode
- Mobs can no longer detect your armor when affected by True Invisibility
- Fixed geckolib armor anchor points causing misaligned armor models when the player is animating
- Fixed JEI recipe autocomplete exploit
- Fixed Raise Dead spell not being able to find suitable ground locations at y < 0

### API
- Added InscribeSpellEvent, courtesy of Silvertide7
- Added ChangeManaEvent
- Added SpellDamageEvent

## <span class="yellow">[2.0.1] (1.19.2 | 1.20.1) 2023-10-02</span>
### Additions
- Added SpellCastEvent and SpellHealEvent for developers, courtesy of Silvertide7

### Changes
- Significantly Optimized WorldUpgrader by skipping uninhabited chunks

### Fixes
- Fix Alchemist Cauldron having a null level when spawned in as a structure

## <span class="yellow">Spell Registration Update [2.0.0] (1.19.2 | 1.20.1) 2023-09-24</span>
### Additions
- New Spells
  - Added Earthquake Spell
  - Added Ray of Frost Spell
  - Added Summon Ender Chest Spell
  - Added Firefly Spell
  - Added Oakskin Spell
- Added Elixirs
  - Added Oakskin Elixir
  - Added Invisibility Elixir
  - Added Evasion Elixir
  - Added Greater Potion of Healing
- Added Firefly Jar block
- Added the Druidic Tome, an epic Nature spell book 
- Added spell targeting success notification
- Added school based resistance attributes
  - While these are not used in the game yet, they can be used by modpacks or addons

### Changes
- Schools
  - Poison School has been replaced by the Nature School
  - Void school has been temporarily removed while it is being reworked
    - Black Hole is now an Ender spell
    - Void Tentacles is now an Ender spell
    - Abyssal shroud is now disabled by default (configurable)
- Spells
  - Devour spell no longer pulls enemies in, and has had its range extended
  - Long casts can no longer be held to cast
  - Long casts must be clicked again to cancel mid-cast
- Mobs
  - Cryomancer, Pyromancer, and Archevoker max health increased by 10
  - Cryomancer, Pyromancer, Archevoker, and Necromancer will now attempt to flee from melee combat
  - Archevoker will now use the Gust spell
  - Increased Arcane Essence drop quantity from the Necromancer
- Textures
  - Updated Anicent Codex, Enchanted Spell Book, and Grimoire of Evokation textures
  - Updated Inscription Table's Lore Page texture
  - Update Amulet of Concentration's texture
  - Updated Wandering Magician, Priest, and Electromancer Chestplate icons to better match their armor model
- Misc
  - Potions can now be put into the Alchemist Cauldron
  - Ink can now be put into the Alchemist Cauldron
  - Ink can now be upgraded in the Alchemist Cauldron
  - The visuals of the Target Area Outline (used in spells like Healing Circle) have been improved

### Fixes
- Fixed an issue causing casting mobs to have a difficult time teleporting around non-flat terrain
- Fixed input issues caused by hybrid long casting inputs
- Fixed Cyromancer's armor attribute not reflecting his worn armor

## <span class="yellow">[1.2.1] (1.19.2 | 1.20.1) 2023-08-10</span>
### Additions
- Added the Decrepit Flamberge sword
- Added error message to the Wayward Compass if there is no found structure

### Changes
- Slimmed down Electromancer Chestplate Model
- Slimmed down Priest Chestplate Model
- Slimmed down Archevoker Chestplate Model
- Removed Black Pixel from Archevoker Shoulderpad
- Updated Archevoker, Pyromancer, Electromancer, and Scarecrow Hat icons
- Updated Archevoker and Electromancer Chestplate icons to better match their models
- Slightly Tweaked Pyromancer Hat model
- Updated Plagued Helmet and Chestplate icons
- Overhauled Ancient Knight animations
- Overhauled Ancient Knight sounds
- Overhauled Ancient Knight energy layer
- Ancient Knights now carry Decrepit Flamberges
- Magehunter sword reworked
- Tweaked Chain Lightning and Healing Circle spell icons

### Fixes
- Fixed Black Holes of small enough radius causing a divide by zero crash

## <span class="yellow">[1.2.0] (1.19.2 | 1.20.1) 2023-07-29</span>
### Additions
- Added the Alchemist Cauldron
  - Allows for scrolls to be recycled into ink
  - Allows for brewing of 4 potions at once
  - Allows for production of Blood Vials
  - Supports interactions with dispensers, hoppers, and observers
- Added Mana Potion, which can be brewed from Arcane Essence
- Added loot integration to all of Yung's structure mods
- Added loot integration to Structory

### Changes
- Priests will now heal friendly players
- Aoe and Cone spells no longer cause knockback
- Instant cast spells no longer spam their cooldown error if right click is held down
- Some loot table rebalances, including ink now dropping outside of Iron's Spellbooks structures

### Fixes
- Fixed Aoe entities damaging summons and teammates
- Fixed Wall of Fire igniting summons and teammates
- Fixed True Invisibility effect icon disappearing

## <span class="yellow">[1.1.8] (1.19.2 | 1.20.1) 2023-07-17</span>
### Additions
- Added spell descriptions to tooltips in Inscription Table and Scroll Forge
- Added config option for the cooldown multiplier of imbued weapons
- Added entity collision to the Shield Spell
- Added JEI descriptions on how to obtain various materials

### Changes
- Updated Affinity Ring Textures
- Updated Arcane Cloth and Ingot Textures
- Level of Vigor gained from Devour Spell is now capped at level 10
- Fang Strike default fang count of increased by 2
- Fang Strike fangs now activate faster
- Fang Strike and Fang Ward base cast time reduced to .75 seconds
- Fang Ward fang count now increases exponentially with its ring count
- Imbued weapons now have half the cooldown instead of twice the cooldown
- Updated to new patchouli book format

### Fixes
- Fixed an exploit that could bypass a spell book's rarity limit when inscribing a spell (fixes #94)
- Fixed an exploit that allowed a different focus to be used to craft a scroll (fixes #100)
- Fixed some magic projectiles ignoring shield spell
- Fixed aoe damage sources damaging shields multiple times
- Fixed Magehunter not showing Counterspell until used
- Fixed casting mobs causing null crash if casting while dying

## <span class="yellow">[1.1.7] (1.19.2 | 1.20.1) 2023-07-06</span>
### Additions
- Added Amulet of Concentration

### Changes
- Redid Icicle Projectile Visuals
- Slowed Down Icicle Projectile
- Redid Icicle Spell Icon
- Redid Snowflake Particle Texture
- Redid Magic Missile Visuals
- Redid Magic Missile Icon
- Replaced Dead King Boss Model and Weapon Model, thanks to Crydigo. Includes Programmer Art Texture Pack

### Fixes
- Fixed Spellcasting Mobs casting Fang Strike while out of range
- Fixed Quick Casting a spell out of bounds of your current spell book causing a crash
- Fixed summoned horse being able to enter a glitched death state if summoned while dying
- Fixed the Dead King not using a second single use spell during his second phase
- Lightning Bolt Spell no longer strikes multiple times
- Fixed latest version of Forge causing loot modifiers to crash game

## <span class="yellow">[1.1.6] (1.19.2 | 1.20.1) 2023-06-26</span>
### Additions
- Added Devour Spell, patreon request of Yorhavich
- Added Patchouli Guide Book
- Added descriptions in JEI for Bottles o' Lightning and Blood vials for how to obtain them
- Added config for Priest House spawn rate

### Changes
- Combined Long and Charge Casts
- Made battlegrounds smaller and more rare
- Reworked Priest House to better fit vanilla and modded villages
- Priest shakes his head like a villager if you interact with him
- Refactored mana bar's hunger Y value calculation to automatically fit with other mods UI elements

### Fixes
- Fixed piglins in the battlegrounds not having weapons
- Chain Lightning can no longer target non-living entities, such as minecarts
- Ceased cancelling the use item finish event
- Magical Area of Effect entities are now affected by counterspell
- Fixed typo in language file causing guiding bolt and chaing lightning death messages to not appear


## <span class="yellow">[1.1.5] (1.19.2 | 1.20.1) 2023-06-20</span>
### Additions
- Added a holy spellcasting mob: the Priest. Spawns in a new house in plains villages.
- Added Guiding Bolt Spell
- Added Chain Lightning Spell
- Added Gust Spell
- Added functionality to modded and vanilla projectiles to pass through players with evasion, instead of thinking there was an impact
- Added Spellbook Category of Equipment to Apotheosis (Thanks to amo)
- Added Poison Apotheosis Gem

### Changes
- Invisibility removes you as the active target from nearby mobs that were targeting you.
- Slimmed down priest armor model.
- Disabled first person animations entirely if both configs are disabled
- Improved casting mob movement logic

### Fixes
- Scroll Forge Ink Outline shifted to match ink texture
- Fixed ground detection that prevented certain spells from working below y = 0
- Fixed and issue where casting mobs could choose to drink a potion and cast a spell at the same time


## <span class="yellow">[1.1.4] (1.19.2 | 1.18.2) 2023-06-08</span>
### Changes

- Updated Counterspell to counter magical effects that were recently added
- Update Scroll Forge ink outline to match new textures
- Shifted all ink textures 1 pixel to the right
- Removed Dismount message when rooted
- Improved mob teleport collision detection

### Fixes

- Target Area Visuals no longer persist if the owner dies while casting
- "None Spell" is no longer craftable
- Fixed Single Use Spell timer improperly being ticked, resulting in some mobs never casting it
- Fixed Crash when attempting to slot a spell into a full spellbook
- Fixed some spells not serializing damage

<hr>


## <span class="yellow">[1.1.3, 1.19.2] 2023-05-31</span>
### Changes
- Replaced ink, hogskin, dragonskin, and most spell book textures (Courtesy of Crydigo)
- Increased spell power bonus from 2.5% to 3% on school armor
- Increased spell power bonus on upgrades from 2.5% to 3% per upgrade
- Increased spell resistance upgrade bonus from 2.5% to 6%
- Increased cooldown upgrade bonus from 5% to 6%
- Update Chinese Translations

### Fixes
- Fixed playeranimator not displaying dependencies screen when the game was launched without it
- Fixed necromancer accidentally having only 1 spell

<hr>

## <span class="yellow">[1.1.2] 2023-05-27</span>
### Changes
- Ray of Siphoning render overhaul
- Firebolt render overhaul
- Fireball render overhaul
- Replaced vanilla fireballs with new fireball model (configurable)
- Added School to a spell's configuration
- Added client config for hiding mana bar text
- Added Fire Bomb, Starfall, and Healing Circle Spells
- Cloud of Regeneration is now disabled by default (won't take effect in preexisting world, reset your serverconfig)
- Added Affinity Rings, which give + 1 level to a random spell
- Added item model override support to scrolls and affinity rings
- Replaced all ring textures (thanks to crispytwig)
 
### Fixes
- Fixed Ancient Knight rendering at improper scale and color with shaders
- Fixed Dead King teleport collision check
- Fixed casting mobs improperly tracking aggression
- Fixed imbued weapon overlay not disapearing after dropping imbued item
- Fixed casting mobs being able to reuse a single use spell if the player relogs or goes out of combat
- Added null check to tooltip renderer

<hr>

## <span class="yellow">[1.1.1] 2023-05-19</span>
### Changes
- Updated Chinese Language File
- Renamed Poison Breath to Poison Spray (No other changes)
- Adjust Black Hole cast animation
- Reduced default max level of blight from 10->8 (will not take effect in preexisting worlds)
- Increase Aspect of the Spider default cooldown from 35s->90s (will not take effect in preexisting worlds)
- Added Blood Needles Spell
- Added Acupuncture Spell
- Increased Ray of Siphoning lifesteal rate from 35%->100%
- Increase Blood Slash lifesteal rate from 10%->15%
- Updated Spell Descriptions to include lifesteal rate
- Added error message if you try to cast a targeted spell with no target
- Redid Void Tentacles texture, also fixing shaders issue with the previous texture
- Redid Void Tentacle spell icon
- Fixed Spell Book Advancement Chain and added Dragonskin Spell Book to the chain

<hr>

## <span class="yellow">[1.1.0] 2023-05-12 - Poison Update</span>
### Changes
- New School Added: Poison
  - Corresponding Rune, Upgrade Orb, and Armor (The Plagued Armor Set)
  - Poison Breath Spell
  - Poison Arrow Spell
  - Poison Splash Spell
  - Acid Spit Spell
  - Aspect of the Spider Spell
  - Blight Spell
  - Root Spell
- Evoker Fort reworked:
  - Removed Library Floor
  - Decreased Spawn Rate
  - Moved loot to be harder to grab without fighting anything 
  - Known Issue: Captured Villagers do not adopt the biome of where they spawn
- Spell Balance Changes:
  - All "basic attack" spells deal more damage at lower levels, and less damage at higher levels
  - All cone spells have reduced damage scaling
  - Most "advanced attack" spells cooldown reduced
  - Shield is now larger, has significantly increased health, and can cast farther away from the player
- Loot Table Changes:
  - Reduced Vanilla Chest Scroll Drop chance
  - Increased rune drop chance in nether chests
  - Increased rune drop chance in catacombs chests
  - Increased rune drop chance in treasure chests
  - Reduced ink drop rates overall
  - Ink now drops from killing wizards and the dead king
  - Corresponding runes now drop from wizards
- General Changes:
  - Extended All Summons duration to 10 minutes instead of 3
  - Reworked Dragon Breath Pools
  - Continuous Tooltips are now in mana per second
  - Tooltips say charge time instead of cast time for charge casts
  - Teleports can now go through water
  - Added Mana command
  - Added Poisonward Ring (immune to poison)
  - Wizards now drink potions instead of spamming heal spell
  - Necromancer Spawn Rates significantly reduced
  - Rebalanced the spell arsenal of the necromancer, archevoker, cryomancer, and pyromancer
  - JEED Support
  - Apotheosis Initial Support (more to come)
  - Ascension now charges creepers
  - New Void Spell
  - Cryomancer in Mountain Tower now guards the loot instead of being useless at the top of the tower
  - Ancient Knights are now immune to fall damage and fire damage, and will lunge more frequently
  - Added Shriving stone, which can remove imbuements or upgrades in the smithing table
  - Increased Copper, Iron, and gold spell book capacity by 1 (will not take effect on old spell books)
  - Decreased Villager Bible Rarity to epic
  - Added new legendary spell book, the Dragonskin Spellbook (+10% Ender Power). Crafted From Dragonskin, a new ender dragon drop
  - Added Dragonskin
  - Gave +20% cooldown reduction to the Ancient Codex

### Fixes
- Fixed precast sounds sometimes playing at the wrong time on the client
- Fixed Missing pixels on Cultist and Priest Armors
- Fixed Client duplicating teleport particles
- Fixed Broken Inscription Table generation in mountain tower

<hr>

## <span class="yellow">[1.0.9] 2023-05-12</span>
### Changes
- Added new Mana UI config (Anchoring, Display mode, and XP mode)
- Casting errors moved from chat onto the action bar
- Generified imbuement and added imbuement config overrides, so you can now imbue anything

### Fixes
- Fixed additional dimensions causing mana regen issues
- Made rarity config thread-safe to actually prevent another REI related issue
- Fixed Summon Timer effect not immediately syncing to client after player respawn

<hr>

## <span class="yellow">[1.0.8] 2023-05-06</span>
### Fixes
- Hotfix to make loading rarity config thread safe to prevent an REI related crash

<hr>

## <span class="yellow">[1.0.7] 2023-05-03</span>
### Changes
- Summons now show death and despawn messages to their owner
- Summons now actively track their number through the pre-existing timer effect (mouse over in inventory to see how many are remaining)
- Summons now remove their effect timer if all summons are dead
- The summon effect timers are not wiped after player death
- Added summon damage attribute, which increases your active summon's damage
- Added Conjurer's Talisman, a necklace that gives +10% summon damage
- Increased Summoned Polar Bear's speed
- Summons and Tamed Animals can no longer agro each other
- Reworked fog particle to be significantly more visually appealing (currently only used in the Void Tentacle spell)

### Fixes
- Fixed a bug where summoned skeleton arrows could anger other summons
- Fixed Summoned Polar Bear not letting the player on after the player dies and respawns
- Fixed Black Pixels appearing around certain spells with some visual mods/shaders
- Fixed the tree half of the Evoker Fort being able to clip into the ground
- Fixed invalid rarity config entries being able to crash the game when looking at a tooltip

<hr>

## <span class="yellow">[1.0.6] 2023-05-03</span>
### Fixes
- Replaced most textures that used vanilla textures. This caused issues with texturepacks, especially ones using Optifine. While this does not extend compatibility for these texture packs, it alleviates conflict with them.

<hr>

## <span class="yellow">[1.0.5] - 2023-05-02</span>
### Fixes
- Fixed Dedicated Server Startup Issue https://github.com/iron431/Irons-Spells-n-Spellbooks/issues/15

<hr>

## <span class="yellow">[1.0.4] - 2023-05-01</span>
### Changes
- Added Spawn eggs for the Archevoker, Necromancer, Cryomancer, Pyromancer, Ancient Knight, and Dead King
- Added conflig for Mana Bar position offset in client config
- Added Tetra Material Support
- Arcane Ingot (metal, gives mana)
- Arcane Cloth (fabric, gives cooldown reduction)
- Hogskin (skin, gives new mana siphon effect)
- Runestones (socket, gives corresponding spell power)
- Frozen Bone (bone, gives freezing effect)
- Added Chinese Language Support (Thanks LILPRINCES)

### Fixes
- Improved Mangrove hut placement fix
- Cleaned up summoned entities, fixing https://github.com/iron431/Irons-Spells-n-Spellbooks/issues/8
- Fixed empty spell wheel log spamming
- Slightly tweaked loot table balance

<hr>

## <span class="yellow">[1.0.3] - 2023-04-29</span>
### Initial Release
- Over 55 upgradable spells
- Over 20 equipment items
- Weapon Imbuement System
- Armor Upgrade System
- 10 wizard armor sets
- 5 randomly generated structures
- 5 new enemies; a new boss
- And much more!


