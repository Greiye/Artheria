2025 March 3

## Fashion System Design Document

This document outlines the design for an in-game fashion system that encourages players to explore diverse clothing options beyond pure stat optimization.  It incorporates social elements, status effects, and maintenance mechanics.
This is for Immersion Sims

### I. Core Mechanics

* **Clothing Attributes:**  Each clothing item possesses the following attributes:
    * `ClothingID`: Unique identifier for each clothing item.
    * `DirtyProgress`: Tracks the cleanliness of the item (0-100%).
    * `NPC_ClothingIDSeen`:  Records clothing items seen worn by NPCs.
    * `ClothingWorn`: Tracks duration an item has been worn.
    * `TotalStylePoints`:  Overall style score contributed by the item.
    * `Accessory Cleanliness`: Cleanliness specifically for accessories.
    * `Accessory Style Points`: Style points specifically for accessories.

* **Hidden Stats:**  Several stats (`AdvancedClothingHideShow`) are hidden from the player to avoid overwhelming them with information, but are tracked in the background.

* **Fashion Seasons:** Fashion trends change seasonally, cycling through +1 (in style), -1 (out of style), and 0 (neutral).  This cycle repeats. *// Fashion changes every season. Fashion can be in style or out of style for the season. Fashion goes from +1, to -1, to 0, then repeats.  *

* **NPC Perception:** NPCs react to the player's clothing based on style, cleanliness, and how long it's been worn.  They also remember what the player has worn previously.

* **Accessories:** Accessories contribute additional style points, granting social bonuses.

### II. Statuses

* **"Ready for Adventure":**  Activated when all relevant stats (excluding health) are above 90%.  Disables mana caps (unlocking an additional 10-20% of the mana bar) for 20 minutes real-time.  This is achievable through the "Maintain Stats" button (see below).

* **"Unfashionable":** Applied when the player wears out-of-date clothing.  Prompts the player to check current fashion trends via in-game magazines or bulletin boards.

### III. Social Interactions

NPC dialogue dynamically changes based on the player's fashion choices.  Examples:

* Positive: "I like that __ you're wearing." / "Your armor's glistening."
* Negative: "Sir, that's looking a little..." / "That's so out of season." / "That's dirty." / "You stink."

### IV. Automation and UI

* **"Maintain Stats" Button:**  Allows the player to automatically refresh core stats to 90%.  Character performs actions like eating, sleeping, cleaning, and repairing. They will 

* **Location-Based Outfit Switching:**  Automatically switches to designated "public wear" upon entering safe zones like camps, towns, or cities.

### V. Perks and Social Classes

* **Privileged Perk:** Unlocks the fashion system.  Not available to characters with the "Street Rat" background.

* **Highborn Perk:**
    * Benefits: Literacy, increased mission rewards, positive interactions with other highborns, unique accent.
    * Drawbacks: Must maintain fashionable attire to retain perk benefits, negative interactions with lowborns.

* **Lowborn Perk:**  Grants positive interactions with other lowborns.

### VI. Dialogue System

* **Keyword-Based Dialogue:**  Expands dialogue options based on keywords used, similar to Morrowind's system.

* **Accent Mechanic:**  Influences dialogue based on the character's accent, accessible through a "sneaky" perk.  This could lead to unique dialogue options or reactions from NPCs.


### VII. Fashion Areas (Equipment Slots)

* Hat
* Mask/Eyewear
* Facewear/Makeup
* Necklace
* Attire Material
* Attire Style
* Attire Color
* Gloves
* Torso (Shirt/Armor)
* Pants
* Shoes
* Social Accessory


### VIII. Stations

* Bed (for sleeping and restoring health)
* Weapon Station (for polishing and maintaining weapons)
* Armor Station (for polishing, cleaning, and repairing armor)
* Washing Station (for cleaning clothes)


### IX. Code Examples (Illustrative)

```cpp
// Example of checking for "Ready for Adventure" status
bool isReadyForAdventure() {
  if (health > 90 && mana > 90 && stamina > 90 && armorCondition > 90 && weaponCondition > 90) {
    return true;
  }
  return false;
}

// Example of applying the "Unfashionable" status
void applyUnfashionableStatus() {
  if (currentFashionTrend != playerClothingStyle) {
    player.addStatus("Unfashionable");
  }
}
```

### X. Design Goals

The primary goal of this system is to encourage players to experiment with different clothing styles and engage with the social aspects of fashion, rather than solely focusing on optimal defense stats.  It adds depth and roleplaying opportunities to the game.


I'm unsure about how "NPC_ClothingIDSeen" is used.  Could you provide more context on how NPCs utilize this information?  Also, how does the "Talking Minigame Mechanics" relate to the fashion system?  More details on the implementation of the accent mechanic and its connection to fashion would be helpful.

Due to this, nobles are also seeking new materials for their clothes.

``` cpp
enum TrendState {
  IN_STYLE = 1,
  NEUTRAL = 0,
  OUT_OF_STYLE = -1
};

struct FashionMaterial {
  std::string name;
  TrendState trend;
  int cycleIndex;  // 0: IN_STYLE, 1: NEUTRAL, 2: OUT_OF_STYLE
};

const TrendState trendCycle[3] = { IN_STYLE, NEUTRAL, OUT_OF_STYLE };

void updateTrend(FashionMaterial &material) {
  material.cycleIndex = (material.cycleIndex + 1) % 3;
  material.trend = trendCycle[material.cycleIndex];

  // When material is "Out of Style," its technology is considered lost.
  if (material.trend == OUT_OF_STYLE) {
    initiateRediscoveryQuest(material);
  }
}

void initiateRediscoveryQuest(const FashionMaterial &material) {
  // Trigger radiant quest mechanics for rediscovery.
  // This function would handle quest initiation and narrative updates.
  std::cout << "Quest initiated: Rediscover the lost technology of " << material.name << ".\n";
}

// Example of updating material trends on season change
void onSeasonChange(std::vector<FashionMaterial> &materials) {
  for (auto &material : materials) {
    updateTrend(material);
  }
}

```