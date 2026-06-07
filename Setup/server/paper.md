# Paper Server Setup

Paper is a high-performance fork of Spigot with extra optimizations and advanced configuration options.

## Requirements

- Java 17 or newer
- A dedicated server folder
- The latest Paper jar
- Port `25565` free for the server

## Steps

1. Create a server folder.
   - Example: `C:\Minecraft\paper`
2. Download the latest Paper jar from https://papermc.io/downloads.
3. Place `paper.jar` in the server folder.
4. Create a `start.bat` file for Windows or `start.sh` for Linux.

### Example Windows start command

```bat
java -Xms1G -Xmx2G -jar paper.jar nogui
pause
```

5. Run the server once to generate initial files.
6. Accept the EULA by changing `eula=false` to `eula=true` in `eula.txt`.
7. Restart the server.

## Configuration

Paper adds custom settings in `paper.yml` and `spigot.yml`.

- `settings.use-shared-cache` - helps performance
- `async-chunks` - improves chunk loading speed
- `mob-spawn-range` - reduces server load

Edit `server.properties` for world settings and player limits.

## Plugins

1. Place plugin jar files into the `plugins` folder.
2. Restart the server to load them.
3. Use `plugins/` and console logs to verify plugin loading.

## Notes

- Paper is generally the best choice for performance and compatibility.
- Keep `online-mode=true` for public servers.
- If you plan to use a proxy, configure `bungeecord: true` in `paper.yml`.
- Back up your world before major changes.

## Recommended next step

Read `../docs/tutorial.md` to understand why Paper is often recommended for plugin servers.
