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

.yellow2 {
color:rgba(223, 187, 0, 0.91)
}

.yellow3 {
color:rgba(0, 120, 36, 0.81)
}
</style>

<hr>

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


