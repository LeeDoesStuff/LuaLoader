# LuaLoader
Loader for CruelHub: asks for a key, then runs the right script for the game you're in.

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/LeeDoesStuff/LuaLoader/main/loader.lua"))()
```

- `loader.lua` is the public entry point.
- `keysystem.lua` is the Panda Auth key screen (CruelHub-themed). A valid key loads the Kryptic Vault script, which loads the game script.
- **Get Key** copies the key link; finish the checkpoints, paste the key, press **Submit**.
- A valid key is saved to your executor's workspace (`cruelhub_key.txt`), so you're only asked again when it expires.

Supported games: Build A Battle Bot, Warfare, Hit The Thrift, Command An Army, Fix It Up!, Sneaker Resell Simulator, Needle in a Haystack, JJBI and Mog or Die.
