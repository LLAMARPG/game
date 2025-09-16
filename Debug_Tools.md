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

#### Verbose identifiers:

These are used by the above `/verbose` command.

Many identifiers will have client and server versions of them. In offline, the client and server versions both toggle the same boolean. You only need to use one identifier to toggle the boolean for both client and server. The client identifier is preferred, but there's no harm in using the server identifier. In online, the client identifiers are for the client specifically and the server identifiers are for the dedicated server specifically.

- `cenc` Client encoding. When you want to see a verbose detail of the client's encoding and decoding. Extremely noisy (lots of spam and text).
- `senc` Same as `cenc` but for the server.
- `cpack` Client packet debugging. When you want to see when the client sends and receives any packet, both in their object and encoded data. This only works in online! Has no effect in offline.
- `spack` Same as `cpack` but for the server.
- `cpackt` Client packet traffic debugging. When you want to see when the client sends and receives any packet, purely in the object form. Works for both online and offline.
- `spackt` Same as `cpackt` but for the server.

#### Debug identifiers:

These are used by the above `/debug` command.

- **New!** `spell_access_all` Enables the selection of all allocated spells in combat, ignoring the spellbook.
- `damage_roll_max` Forces IntRange (used by the data system, an object that stores a range and rolls randomly inside of it) to roll the maximum value every time.
