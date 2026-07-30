![Logo](https://raw.githubusercontent.com/Michy1212/FFA-Randomizer/refs/heads/main/images/Logo.png)

# Final Fantasy Adventure Randomizer

The aim of this document is to provide important information about the Final Fantasy Adventure Randomizer.

## Which version of the game can be randomized?
Currently, only the US version can be randomized. The randomization software will check your ROM's CRC32 to ensure that it is compatible.

## What is randomized in the game?
Shops and chests (items and equipment) are randomized.

Some shops share the same inventory on the overworld. For example, the Battle Axe shop uses the same inventory as the Wendel Item Shop. Here is the list of shared shops:
- Topple Item Shop (2) / Kett's Area Item Shop / Wendel Item Shop
- Menos Item Shop / Jadd Item Shop / Mt. Rocks Item Shop / Glaive Castle Item Shop / Ish Item Shop / Snowfield Item Shop / Float Rocks Item Shop / Watt's Shop
- Float Rocks Magic Shop / Crystal Desert Magic Shop

Magic spells can also be randomized, either among spell locations only or within the unique chests (such as the Rusty Sword, Iron Shield, Mirror, etc.).

You can also randomize followers' abilities, except for the Chocobot and Watts.

The Chocobot can be placed at a randomized location using a Lua script (BizHawk emulator required).

## Which items can appear in shops?
Any item can appear in shops except those that do not have a proper price assigned in the original ROM. This includes the Rusty Sword, Mirror, and Amanda's Tears.  
These items were excluded because, when sold in shops, they cost 65,025 GP, which is the maximum value the game can handle.  
All other items and equipment can appear in shops, even XCalibur!

## What modifications have been made to the original game?
Only modifications intended to prevent softlocks or preserve story logic have been made. Map changes were created using patches generated from a ROM edited with Mystic Editor.

- Some leaves have been removed, allowing the player to access the chest and avoid a potential softlock if they save without having the Sickle.  
  **Before:**  
  ![Before](images/before_leaves.png)  
  **After:**  
  ![After](images/after_leaves.png)

- To obtain the Chain chest, you must already have the Chain. When this chest is opened, the door in Lee's room closes, and the only way to make Lee appear is by obtaining Fuji, so having a Chain.  
  **Before:**  
  ![Before](images/before_chain.png)  
  **After:**  
  ![After](images/after_chain.png)

- If you obtain an early Chocobot and leave it behind during the early game, you may be unable to retrieve it and could softlock your game.  
  To prevent this, land has been added between Menos and the Airship Area, allowing you to return (only when the Chocobot is placed early).  
  **Before:**  
  ![Before](images/before_chocobot.png)  
  **After:**  
  ![After](images/after_chocobot.png)

- To prevent softlocks in Glaive Castle, the bridge before the castle (which normally collapses) remains available, allowing the player to return to Mt. Rocks.  
  The cutscene will still destroy the bridge, but it will reappear after reloading the screen.

  ![Bridge to Glaive](https://raw.githubusercontent.com/Michy1212/FFA-Randomizer/refs/heads/main/images/Bridge%20to%20Glaive.png)

- Other changes:

| Aim | Original game | Randomizer |
|-----|---------------|------------|
| Obtain Bogard's chest | Save Fuji for the first time and visit Bogard's house with her | Simply visit Bogard |
| Obtain Heal | Go to Wendel | Save Fuji from Lee |
| Trigger Fuji's first Airship dialogue | Defeat Megapede | Simply talk to her |
| Prevent the Airship from taking off | Avoid progressing too far in the story | The Airship remains grounded |
| Obtain the Bone Key | Defeat the Dark Lord and Kary | Defeat Kary |
| Reverse the waterfall leading to the Temple of Mana | Defeat Kary | Defeat Garuda |

## Why is the Silver chest an option?
In the original game, the Silver Chest only exists for story purposes and does not contain any item. Enabling this option turns it into a real chest that becomes part of the randomization pool. Because this chest is unique, it may contain a spell if you choose to randomize spells into unique chests. The goal is to avoid having an empty or "dead" dungeon reward.

## Why are throwable items an option?
Because chest contents are randomized, you may obtain multiple Sickles, Chains, Battle Axes, Stars, Rusty Swords, or XCaliburs. If your equipment inventory becomes full of these progression items, you may be unable to pick up additional equipment. This option allows you to discard them when necessary.

## My Chocobot disappears when I save Fuji or travel with Bogard. What should I do?
Don't worry. Even if the Chocobot is no longer visible, it remains with you. It will reappear when you reload your save thanks to code created by Dagmor.

## When exiting a city or dungeon, my Chocobot is gone. What should I do?
This can happen in certain locations, such as after defeating Hydra. The Chocobot is usually nearby but off-screen. Simply reload the area and it should reappear.

## I entered the Airship and the Chocobot didn't come with me. What happened?
The Chocobot is still accompanying you.  
Although it is not visible and cannot be mounted while inside the Airship, it will reappear after you leave the Airship or after completing the Airship Dungeon and exiting to Menos.

## The items in Topple's shop have changed! What's happening?
When you obtain Bogard's chest or visit the next shop (the one selling the Battle Axe), the game's script changes Topple's shop inventory to match the shared inventory used in Wendel, Kett's Area, and other locations.  
To prevent mandatory progression items from disappearing, such items will never appear in the first version of Topple's shop.

## I found an early or mid-game Chocobot, but it is only a Chocobo. How can I travel overseas?
Visually, it appears as a Chocobo. However, once mounted, it transforms into the Chocobot, allowing you to travel almost anywhere.

## On which platform or emulator can I play the Randomizer?
If the Chocobot remains in its original location, you can play on any platform that supports the original game.  
However, if the Chocobot is placed in a different location (before Ish), BizHawk is required.  
A Lua script is used to move the Chocobot on the overworld, and this script is automatically generated by the randomization program.  
Currently, moving the Chocobot directly through ROM modifications is not working reliably.  
When starting a seed that uses the Chocobot Lua script, make sure the script is running correctly (you should see the logo).

## Known issues
If you obtain an item or piece of equipment from a magic spell location (when spells are randomized into all unique chests) while your inventory is already full, the item may be lost and the game may crash.  
This happens because these checks are not actual chests and therefore do not perform the normal inventory-space verification.  
Be sure to save before collecting any of the following checks:
- Cure
- Sleep
- Heal
- Mute
- Lit
- Nuke
- XCalibur

## Other notes
- The item or equipment obtained from the Battle Axe sale has a modified resale value. Since an expensive item could otherwise be purchased for only 150 GP and repeatedly sold for profit (because it is restocked when no longer owned), its resale value has been reduced to 75 GP.
- Some item names and spell names may appear truncated. This is normal. Different chests have different amounts of available text space, so names are shortened to fit. For example, “![Potion](https://raw.githubusercontent.com/Michy1212/FFA-Randomizer/refs/heads/main/images/Potion.png) Unicorn.” requires 8 bytes, but only 5 bytes are available for the Ether chest, so “![Potion](https://raw.githubusercontent.com/Michy1212/FFA-Randomizer/refs/heads/main/images/Potion.png) Unic” will be displayed.
