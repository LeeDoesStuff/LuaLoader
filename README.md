# LuaLoader
Loader for CruelHub: asks for a key, then runs the right script for the game you're in.

> [!IMPORTANT]
> ## 🔑 Skip the ads: get an AD-FREE key on our Discord
> Join **[discord.gg/ka8sqyajju](https://discord.gg/ka8sqyajju)** to generate a key with no ad checkpoints.

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/LeeDoesStuff/LuaLoader/main/loader.lua"))()
```

- **Get Key** copies the key link; finish the checkpoints, paste the key, press **Submit**.
- A valid key is saved to your executor's workspace (`cruelhub_key.txt`), so you're only asked again when it expires.

Supported games: Build A Battle Bot, Warfare, Hit The Thrift, Command An Army, Fix It Up!, Sneaker Resell Simulator, Needle in a Haystack, JJBI, Mog or Die, Pixel Conquest, Death Ball, Junk Crushers 2, Ball VS Ball and Trade Up.

Any other game loads the universal script (ESP, fullbright, walkspeed, jump).

## Adding a game

`loader.lua` never changes when you add a game. The loader looks the game up in `games.json`, so a new game is two steps.

1. **Put the script in the CruelHub scripts repo** as `<game-folder>/<script>.lua` (for example `trade-up/tu_main.lua`).
   - Guard it to its own place, so it does nothing anywhere else: `if game.PlaceId ~= <placeId> then return end`.
   - Use the CruelHub look like the other hubs: the Obsidian UI with `ShowCustomCursor = false`.

2. **Add one line to `games.json` in this repo:**
   ```json
   "<universe id>": "<game-folder>/<script>.lua"
   ```
   - The key is the game's **universe id, not its place id.** Get it from `https://apis.roblox.com/universes/v1/places/<placeId>/universe`. The `"universeId"` in the answer is what goes here.
   - The value is the script's path in the scripts repo, or a full `https://` URL.
   - Put a comma after the line above yours. One missing comma breaks the whole file, and every game stops loading.
   - Leave `"build"` and `"default"` as they are.

Then add the game's name to **Supported games** above, and open a PR (or push to `main`).

Changes are live in about 5 minutes (GitHub's raw cache). To test, join the game and run the loadstring above. Your hub should open after the key screen.
