# Velocity Proxy Setup

Velocity is a modern Minecraft proxy focused on performance, security, and reliable forwarding.

## Requirements

- Java 17 or newer
- Backend servers running Paper or compatible server software
- Port `25577` available for the proxy

## Setup steps

1. Create a proxy folder.
   - Example: `C:\Minecraft\proxy`
2. Download the latest Velocity jar.
   - Official: https://velocitypowered.com
   - GitHub releases: https://github.com/PaperMC/Velocity/releases
3. Place `velocity.jar` in the proxy folder.
4. Create a `velocity.toml` file in the same folder.
5. Create a `plugins` folder if you want Velocity plugins.

## Example `velocity.toml`

```toml
[servers]
  hub = { address = "127.0.0.1:25565", motd = "Hub Server", restricted = false }
  survival = { address = "127.0.0.1:25566", motd = "Survival Server", restricted = false }

[forced-hosts]
  "play.example.com" = "hub"

[advanced]
  player-info-forwarding-mode = "MODERN"
  compression-level = 6

[metrics]
  enabled = true

[connection]
bind = "0.0.0.0:25577"

[query]
  enabled = false

[security]
  force-key = ""
```

## Backend server configuration

On each backend server:

- Set `online-mode=false` in `server.properties`
- Use `velocity.toml` forwarding if supported by your server version
- Use local ports like `25565`, `25566`, `25567`

## Starting Velocity

Run:

```powershell
java -Xms1G -Xmx2G -jar velocity.jar
```

## Notes

- `player-info-forwarding-mode = "MODERN"` is recommended for newer Paper versions.
- For older backends, `LEGACY` forwarding may be required.
- Set `force-key` only if you want Velocity to validate backend connections.

## Recommended next step

Read `../docs/proxy-server.md` for proxy comparisons and use `../setup/proxy/README.md` for setup guidance.
