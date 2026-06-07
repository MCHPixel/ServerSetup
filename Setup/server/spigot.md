# Spigot Server Setup

Spigot is a Bukkit-compatible Minecraft server with performance improvements and good plugin support.

## Requirements

- Java 17 or newer
- A dedicated server folder
- BuildTools or a prebuilt Spigot jar
- Port `25565` free for the server

## Steps

1. Create a server folder.
   - Example: `C:\Minecraft\spigot`
2. Download BuildTools from https://www.spigotmc.org/wiki/buildtools/ if you want the latest server jar.
3. Run BuildTools to create `spigot-<version>.jar`.
   - Example:

```powershell
git clone https://hub.spigotmc.org/stash/scm/spigot/buildtools.git
cd buildtools
java -jar BuildTools.jar --rev latest
```

4. Move `spigot-<version>.jar` into your server folder and rename it to `spigot.jar`.
5. Create a `start.bat` file for Windows or `start.sh` for Linux.

### Example Windows start command

```bat
java -Xms1G -Xmx2G -jar spigot.jar nogui
pause
```

6. Run the server once to generate initial files.
7. Accept the EULA by changing `eula=false` to `eula=true` in `eula.txt`.
8. Start the server again.

## Configuration

Edit `spigot.yml` and `server.properties` to tune server behavior.

- `bungeecord` - set to `true` only if using a proxy
- `view-distance` - lower values improve performance
- `online-mode` - usually `true` for public servers

## Plugins

1. Place Bukkit/Spigot plugin jars into the `plugins` folder.
2. Restart the server to load them.
3. Check `plugins/` logs for compatibility warnings.

## Notes

- Spigot is a good balance of performance and compatibility.
- Use `paper.yml` or Paper if you need additional optimizations.
- Back up your server files regularly.

## Recommended next step

Read `../docs/tutorial.md` to compare Spigot with Paper and Bukkit.
