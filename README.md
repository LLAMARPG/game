# 0.6.1.0

- Fixed several UI bugs with NPCs.
- Fixed wrong Steam app id being used for Playtest.

# 0.2.0

- Fixed being unable to select spell or item actions in combat
- Fixed items being dropped into the world being mistakenly treated as a traded item and poofing due to no active trade
- Implemented combat music
- Fixed music not looping
- Implemented disabling global chat
- Fixed several rendering issues with panels
- Fixed being able to store items outside of the bounds of the inventory, this caused a save file format change which bricks all existing characters before this version. Offline will delete them automatically, online will not, be sure to delete them yourself. You will not be able to load them under any circumstances

# 0.1.0

- Implemented deleting items from the inventory, the unlisted keybind is Ctrl + Shift + Right Click the item
- Fixed player level and experience were not updating in the character screen
- Limited characters in a chat message to 255
- Fixed being able to select the spell or item action by themselves without actually clicking on an item or spell in combat
- Fixed items suddenly poofing when equipping and then relogging
- Other monsters now have sprites that aren't Rock
- Implemented character/monster name and level display for both parties in combat
- Fixed health, mana, and stamina not syncing properly client-side on rejoins or on usage of the healing vendor or potions
- Implemented escaping in combat
- Implemented stealing another player's gold when winning in PvP combat
- Fixed multiplayer actor syncing crashing the game
- Fixed item requirements not displaying in red when the requirements weren't met
