# Bukkit Server Setup

Bukkit is a classic Minecraft server platform with strong plugin compatibility. It is easy to configure, but note that Bukkit development is limited compared to Spigot and Paper.

## Requirements

- Java 17 or newer
- A dedicated server folder
- A compatible Bukkit jar file
- Port `25565` free for the server

## Steps

1. Create a server folder.
   - Example: `C:\Minecraft\bukkit`
2. Download the latest Bukkit server jar.
   - Start at https://dev.bukkit.org/projects/bukkit/files or community mirror downloads.
3. Place the downloaded `bukkit.jar` in the server folder.
4. Create a `start.bat` file for Windows or `start.sh` for Linux.

### Example Windows start command

```bat
java -Xms1G -Xmx2G -jar bukkit.jar nogui
pause
```

5. Run the server once to generate initial files.
6. Accept the EULA by opening `eula.txt` and changing `eula=false` to `eula=true`.
7. Start the server again to complete initial setup.

## Configuration

Edit `server.properties` to configure your server:

- `level-name` - world folder name
- `motd` - server message of the day
- `max-players` - allowed player count
- `online-mode` - keep `true` for online authentication

## Plugins

1. Create a `plugins` folder if it does not already exist.
2. Download Bukkit-compatible plugins.
3. Place plugin jar files into the `plugins` folder.
4. Restart the server to load plugins.

## Notes

- Bukkit may lag behind the latest Minecraft versions.
- For better performance and more active development, consider Paper or Spigot.
- Keep backups of your world and config files.

## Recommended next step

Read `../docs/tutorial.md` to compare Bukkit with Spigot and Paper.
