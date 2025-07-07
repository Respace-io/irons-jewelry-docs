---
layout: post
icon: fa-solid fa-list-ul
order: 20
toc: true
---

<style>
.yellow {
color:rgba(255, 194, 41, 0.5);
}

.yellow2 {
color:rgba(223, 187, 0, 0.91)
}

.yellow3 {
color:rgba(0, 120, 36, 0.81)
}
</style>

<hr>

## <span class="yellow"> [1.5.0] (1.21.1) 2024-07-06</span>
### Additions
- Added Rhinestone Amulet necklace pattern
  - Is crafted from a chain and three separate rhinestone gems
  - Grants an attribute from each gem
  - Can be found in normal high-quality-pattern sources
- Added Jewelry title merging
  - Jewelry item names with repeated part materials will be consolidated into one word
  - ie: Superior Diamond-Diamond Ring -> Superior Diamond Ring

### Fixes
- Fixed the existence of `partForQuality` part not being strictly enforced in a pattern definition. Patterns will now fail to load if there is a mismatch, instead of presenting undefined behavior in-game.

## <span class="yellow"> [1.4.1] (1.21.1) 2024-05-31</span>
### Fixes
- Fixed jewelcrafting table exploit
- Fixed loot injections targeting modded directories
- Fixed nullable JEI logic

## <span class="yellow"> [1.4.0] (1.21.1) 2024-05-08</span>
### Additions
- Added Bane Ring pattern
  - Grants action on melee hit

### Changes
- Restyled Onyx textures to be brown instead of dark blue
- Increased rate at which Jeweler trades give Villager Xp
- Adjust scaling of attribute based rings
  - Superior Ring now no longer gives an inherit bonus over Improved Gemset Ring
- Tweaked Material Bonuses, reducing duplicate bonuses
  - Netherite
    - Reduced Action (gain strength) effect duration from 6s -> 3s
  - Moonstone
    - Negative Effect: Blindness -> Weaving (no longer duplicates Onyx)
  - Lapis
    - Added Glowing as Negative Effect (previously nothing)
  - Garnet
    - Added Wither as Negative Effect (previously nothing)
    - Action: Heal -> Grant Self Resistance (no longer duplicates Onyx)
  - Emerald
    - Added Infested as Negative Effect (previously nothing)

## <span class="yellow"> [1.3.0] (1.21.1) 2024-04-25</span>
### Additions
- Added Dynamic Loot Injections for Jewelry items
  - Dynamically inserts jewelry items into loot tables based on the loot table's contents above some threshold
  - Loot tables with more gems, equipment, or other tagged items have a higher change to generate jewelry
  - Added corresponding item tags: `loot_handler/low_gearscore`,`loot_handler/medium_gearscore`,`loot_handler/high_gearscore`,`loot_handler/very_high_gearscore`
- Added Serverconfig file, with options for disabling loot injections and changing jeweler house weight
- Added Japanese localization, thanks to Mohuzato
- Added Russian localization, thanks to Heimdallr

### Changes
- Adjusted Barbed Band texture

### API
- Now requires Atlas API v1.1.0, and cannot exceed v1.2.0 (exclusive)

## <span class="yellow"> [1.1.0] (1.21.1) 2024-04-14</span>
### Additions
- Added Ring of Haggling pattern
  - "Unique"-styled ring that gives discount to villager trading when worn
  - Pattern can only be obtained via villager trading

### Changes
- Jei Jewelcrafting previews now use dedicated "Example" material (instead of platinum)
- Jei Jewelcrafting previews now describe their Bonuses granted when crafted
- Pressing Jei "uses" key on an Artisan Scroll now shows the recipe for the contained pattern
- Adjusted Emerald and Copper Palettes
- Adjusted all ring band textures, which now show gem settings where the gems sit, which is visible during intermediary crafting textures

## <span class="yellow"> [1.0.11] (1.21.1) 2024-03-22</span>
### Fixes
- Fixed self-inflicted damage causing stack overflow with protection amulet

## <span class="yellow"> [1.0.10] (1.21.1) 2024-03-19</span>
### Additions
- Added Chinese localizations, thanks to Hanekmio

## <span class="yellow"> [1.0.9] (1.21.1) 2024-02-25</span>
### Fixes
- Jewelry trades can no longer generate with a secondary cost of zero

## <span class="yellow"> [1.0.8] (1.21.1) 2024-02-15</span>
### Fixes
- Jewelry trades can no longer generate with a cost of zero

## <span class="yellow"> [1.0.7] (1.21.1) 2024-02-06</span>
### Fixes
- Fixed JewelryData equals implementation

## <span class="yellow"> [1.0.6] (1.21.1) 2024-02-02</span>
### Changes
- Added all possible Artisan Scroll items to creative menu and JEI

### Fixes
- Fixed Jewelcrafting Station block not having an effective tool (now axe)

## <span class="yellow"> [1.0.5] (1.21.1) 2024-01-25</span>
### Fixes
- Fixed nullable JEI plugin handling

## <span class="yellow"> [1.0.4] (1.21.1) 2025-01-11</span>
### API
- Updated to official Curios API

## <span class="yellow"> [1.0.3] (1.21.1) 2024-12-27</span>
### Fixes
- Fixed tooltip compatibility between Curios API ports

### API
- Now native to 1.21.1
- Now primarily supports Curios API Continuation

## <span class="yellow"> [1.0.2] (1.21) 2024-12-23</span>
### Fixes
- Fixed disconnection issue on dedicated servers caused by material modifiers

## <span class="yellow"> [1.0.1] (1.21) 2024-12-23</span>
### Additions
- Added `MaterialModifiers`

### Changes
- Piglin Signet Ring Artisan Scroll can now drop from Piglin Bartering
  - Roughly 4x more rare than bartering for an enchanted book (0.25% chance)
- Reworked Jewelry Trade Prices
  - More expensive/rare materials are now more expensive
  - Parts that don't contribute to quality are less impactful to the overall price
  - Removed randomness from the prices
  - Prices now stack as emerald blocks if the total is over 64 emeralds, instead of filling both trade slots with emeralds

### Fixes
- Fixed the tooltip of jewelry items display "When worn" header despite giving no bonuses 

## <span class="yellow"> Initial Release - 1.0.0 - </span> <span class="yellow3"> [mc:1.21] - 2024-11-23</span>

### Featuring:
- 2,000+ jewelry combinations
- 7 new obtainable gemstone items
- New Villager Profession
- Datadriven mechanics
- And more!


