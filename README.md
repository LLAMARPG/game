# 0.7.0.0

- Added (technically reverted) to old WASD method. This makes interacting with warps (and other future objects) with WASD seamless.
- Movement system reverted to a chunk caching system. Client stores x frames (currently 60, one second) of movement data and then sends it to the server. Data usage is slightly more efficient. More improvements to data usage in the future.
- Added a debug 'ghost' player. This shows you your position that the server and others see (not accounting for real latency).
- Added debug messages for client's communication with Steam relative to joining online servers. No more fully silent Steam failures. More improvements to come.
- Fixed a bug where the end combat panel could be stuck in the wrong position with the right combination of buttons.
- Fixed a bug where closing an NPC's interact menu inside the Talk option would result in the interact menu opening again on the Talk option rather than the main interact menu.
- Fixed a bug where you would continue walking after combat starts.
- Removed transparency from item and spell descriptions.
- Moved action count text in the combat UI to be a debug-only option.
- Added tabs to the stamina bars to see when one would lose an action count.
- Fixed a bug where you would continue walking when interacting with an NPC.
- You can now use the mouse to interact with NPC and player interact menus.
- On rare occasion, mouse clicking to move would be ignored due to an invisible UI element eating the click.
- Character creation screen has been adjusted visually to make more sense.
- When you create a character, it automatically selects it.
- Volume settings now have sliders.
- New sound and music system implemented. More improvements to come.
- Settings menu has been completely revamped.
- Fixed audio and music not playing. `res://` was being included twice on accident.
- Resistance UI in combat is functional and color coded.
- Stat allocation now instantly confirms rather than being pending and manually confirming after.
- Fixed spells not working in combat.
- Monsters can now drop items other than what they are wearing/using. Right now, only Champions dropping two random potions make use of this system.
- Combat end panel has been improved.
- Implemented character screen order, it is in order of most recently saved or loaded. The online version is completely untested.
- Simple combat attack animations have been added.
- Simple combat attack sounds have been added (arbitrarily chosen sounds for now).
- Floating damage number visuals in combat have been added.
- More combat UI elements have been implemented, including the 'Spell' and 'Gear' buttons as well as the action icons for others in combat.
- Many misc bugs have been fixed.
- Probably other things that I forgot about.

# 0.6.2.1

- Fixed compile error on exported builds preventing game from loading most of its scripts properly.
- Prevented player from moving while interacting with an actor (NPC or other player).
- Added `Open User Folder` to the settings menu next to the Debug toggle for convenience. It will open the folder on your machine where the Godot save and log files are stored.

# 0.6.2.0

- Implemented enforcement of mana and stamina costs in combat. Tested to a basic degree, but not every scenario was tested.
- Fixed items not equipping automatically on first load, forcing you to manually re-equip them.
- Mana total % no longer relative to Stamina total %. They are now mutually exclusive.
- Warp objects made slightly bigger so that WASD movement can interact with it more reliably.
- Fixed not being able to delete offline character files.
- Fixed 'Damage' displaying twice when 0 damage is dealt in an action.
- Fixed Lightning Damage displaying it dealing 0 damage as well as other issues resulting from it.
- Fixed combat log from last combat displaying on new combat start.
- Fixed cave darkening getting stuck on screen during relog if you exited the game while in a cave.
- Fixed leveling up decreasing your spell points instead of increasing them on the spell tree panel.
- Fixed crash when exiting world.

# 0.6.1.0

- Fixed several UI bugs with NPCs.
- Fixed wrong Steam app id being used for Playtest.
- Fixed RPC calls being ignored due to mismatching NodePaths, preventing any kind of server/client communication.

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
