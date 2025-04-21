All dev/debug access stuff is only available in offline, it won't work in online.

In the settings menu, you can enable Debug option to show a few technical things on the screen, such as:
- Pathing
- Current position
- Force Win/Lose buttons in combat
- See enemy items in combat

There are a number of commands to test with (sometimes these break too):
- `/gold [amount]` adds gold to your inventory
- `/save` forces your character file to save immediately
- `/item [level] {item base}` generate a random item with a certain level and an optional item base in your inventory
- `/consumable [item]` generate a random consumable (stuff like potions)
- `/levelup {amount}` level your character up once, or optionally a provided amount of times
- `/respec` reset your stat and spell points
- `/heal` refills all of your resources to the maximum
- `/addmod [modifier name] [value]` adds a specific modifier to the item on your cursor with the specified value.
- `/remmod [modifier name]` removes all instances of a specific modifier from the item on your cursor
- `/encounter [amount] [level] [monster name]` forces combat to start with the amount of monsters at the level provided. Amount cannot be more than 3.
- `/clear` clears the chat
- `/crash` forces the server to crash, probably don't have a need to use this though..
