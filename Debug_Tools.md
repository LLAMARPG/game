All dev/debug access stuff is only available in offline, it won't work in online unless you have dev access.

### In the settings menu, you can enable Debug option to show a few technical things on the screen, such as:
- Pathing
- Current position
- Force Win/Lose buttons in combat.
- See enemy items in combat from the start.
- See combat action count text in combat.
- See your own 'ghost' to see where you are on the server and to other players.
- Client-Steam communication messages on the server selection page (online mode after you choose a character) to see the state of Steam communication.
- Toggle forced encounters from walking with a checkbox next to the stomp/sneak meter.

### There are a number of commands to test with (sometimes these break too):
- **New!** `/minigame` forces the given `minigame` to start. [See identifier list here, under `minigame` column](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1212007594#gid=1212007594).
- **New!** `/profession` a generic command to handle Profession data and logic.
  - `value` subcommand will print the value associated with the given `profession_function` identifier. [See identifier list here, under `profession_function` column](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1212007594#gid=1212007594).
- **New!** `/print` prints a specific message based on the given identifier. See below for identifier list.
- **New!** `/rtmsd` sets the rotating task movement sync thread delay on the server to the given delay in nanoseconds. Unstable command.
- **New!** `/follow` forces a quest-based client-only NPC to follow you using the basic follow logic that exists.
- `/interact` forces an interaction (pressing the interact button) with the specified target.
- `/teleport` or `/tp` teleports the player to the designated significant location. [See significant location identifiers here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1212007594#gid=1212007594).
- `/questaction` or `/qa [quest action key]` forces a quest action to run for a player on both client and server. This should be used sparingly as it has no safety checks and can brick quest states if saved. [See quest action keys here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=124634217#gid=124634217).
- `/objectsetinteger` or `/osi` sets an integer value to a quest object. This can be used to bruteforce quest objects into certain states, but there is no solid list anywhere for what you can change. [See quest object identifiers here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1212007594#gid=1212007594).
- `/waypoint` or `/wp` opens the waypoint menu from anywhere, optional argument of `unlock/u all/[waypoint key]` to unlock a waypoint or all waypoints. [See waypoint keys here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1287109826#gid=1287109826).
- `/spellscribe` or `/ss` opens the spellscribe vendor menu from anywhere.
- `/debug [identifier]` toggles a debug boolean associated with the specified identifier. See below for the identifier list.
- `/refill` refills all flasks in the inventory to max charges.
- `/freecam` toggles freecam. WASD to pan the camera, mouse wheel to zoom in and out, Shift to speed up the panning or the scrolling, and LMB to teleport the player on both client and server to the clicked position.
- `/verbose [identifier]` toggles a verbose logging boolean associated with the specified identifier. See below for the identifier list.
- `/res [resource] [amount]` sets the specified resource to the specified amount 
- `/deplete` sets all your combat resources (except health) to 0
- `/gold [amount]` adds gold to your inventory
- `/save` forces your character file to save immediately
- `/item [level] {item base}` generate a random item with a certain level and an optional item type in your inventory. [See item types here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=464949103#gid=464949103).
- `/consumable [item]` generate a consumable (stuff like potions). [See items here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=273484415#gid=273484415).
- `/levelup {amount}` level your character up once, or optionally a provided amount of times
- `/respec` reset your stat and spell points
- `/heal` refills all of your resources to the maximum
- `/addmod [modifier name] [value]` adds a specific modifier to the item on your cursor with the specified value. [See modifiers here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1961885428#gid=1961885428).
- `/remmod [modifier name]` removes all instances of a specific modifier from the item on your cursor. [See modifiers here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1961885428#gid=1961885428).
- `/encounter [amount] [level] [monster name]` forces combat to start with the amount of monsters at the level provided. Amount cannot be more than 3. [See monster names here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1482007302#gid=1482007302).
- `/clear` clears the chat
- `/crash` forces the server to crash, probably don't have a need to use this though..

### Command line options:
- `--client` loads the game application in client mode.
- `--server` loads the game application in server mode. Requires developer access, as the application shipped through Steam does not contain the server code needed for this to function.
- `--pos:x,y` allows you to specify the location the window is placed on the desktop as soon as the application loads.
- `--char:char_name` allows you to specify which character to automatically select. Only works if the client is set to automatically navigate to a character selection screen.
- `--ip:address` allows you to specify which server to automatically select. Only works if `--char` is provided and successfully completes.

### Feature tags:
- `skiponline` is a client-only feature tag forcing the game application to automatically navigate to the online menu (as if you were clicking `Online` on the title screen) as soon as it loads.
- `dedicated-server-show-world` is a server-only feature tag that enables rendering of the world, players, and some other features in the server's game window. This feature tag is useless without a window (and may even cause errors in headless mode).
- `authentication_steam` is a feature tag used by both client and server to indicate to use Steam authentication process. Without this, online mode is not available. The application shipped through Steam will have this logic enabled by default.

#### Verbose identifiers:

These are used by the above `/verbose` command.

Many identifiers will have client and server versions of them. In offline, the client and server versions both toggle the same boolean. You only need to use one identifier to toggle the boolean for both client and server. The client identifier is preferred, but there's no harm in using the server identifier. In online, the client identifiers are for the client specifically and the server identifiers are for the dedicated server specifically.

- **New!** `rtms` enables verbose logging of movement sync on the server for all players. This is very noisy.
- `zones` or `zone` Enables debug messages for entering, exiting, and encounter checks within zones.
- `cenc` Client encoding. When you want to see a verbose detail of the client's encoding and decoding. Extremely noisy (lots of spam and text).
- `senc` Same as `cenc` but for the server.
- `cpack` Client packet debugging. When you want to see when the client sends and receives any packet, both in their object and encoded data. This only works in online! Has no effect in offline.
- `spack` Same as `cpack` but for the server.
- `cpackt` Client packet traffic debugging. When you want to see when the client sends and receives any packet, purely in the object form. Works for both online and offline.
- `spackt` Same as `cpackt` but for the server.

#### Debug identifiers:

These are used by the above `/debug` command.

- `spell_access_all` Enables the selection of all allocated spells in combat, ignoring the spellbook.
- `damage_roll_max` Forces IntRange (used by the data system, an object that stores a range and rolls randomly inside of it) to roll the maximum value every time.

#### Print identifiers:

These are used by the above `/print` command.

- `inv` or `inventory` prints out the player's inventory to console on both the client and server. Useful for seeing inventory desync bugs.
- `winpos` or `windowposition` prints out the game window's current position your desktop. Useful in conjunction with the position command line option.
