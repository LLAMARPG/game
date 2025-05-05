All dev/debug access stuff is only available in offline, it won't work in online.

In the settings menu, you can enable Debug option to show a few technical things on the screen, such as:
- Pathing
- Current position
- Force Win/Lose buttons in combat (the buttons are always visible right now, the Debug option does not toggle this yet).
- See enemy items in combat (the buttons are always visible right now, the Debug option does not toggle this yet).

There are a number of commands to test with (sometimes these break too):
- `/gold [amount]` adds gold to your inventory
- `/save` forces your character file to save immediately
- `/item [level] {item base}` generate a random item with a certain level and an optional item type in your inventory. [See item types here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=464949103#gid=464949103).
- `/consumable [item]` generate a random consumable (stuff like potions). [See items here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=273484415#gid=273484415).
- `/levelup {amount}` level your character up once, or optionally a provided amount of times
- `/respec` reset your stat and spell points
- `/heal` refills all of your resources to the maximum
- `/deplete` sets all your combat resources (except health) to 0
- `/addmod [modifier name] [value]` adds a specific modifier to the item on your cursor with the specified value. [See modifiers here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1961885428#gid=1961885428).
- `/remmod [modifier name]` removes all instances of a specific modifier from the item on your cursor. [See modifiers here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1961885428#gid=1961885428).
- `/encounter [amount] [level] [monster name]` forces combat to start with the amount of monsters at the level provided. Amount cannot be more than 3. [See monster names here](https://docs.google.com/spreadsheets/d/1kxMXg6sl3DrCN6KrCxsOHNGNPFgZGQDFeIrTebnGlh8/edit?pli=1&gid=1482007302#gid=1482007302).
- `/clear` clears the chat
- `/crash` forces the server to crash, probably don't have a need to use this though..
