# BungeeCord Proxy Setup

BungeeCord is a proxy server that connects multiple Minecraft servers into a single network.

## Requirements

- Java 17 or newer
- One dedicated proxy folder or machine
- Backend servers running Bukkit/Spigot/Paper
- Port `25577` free for the proxy

## Setup steps

1. Create a proxy folder.
   - Example: `C:\Minecraft\proxy`
2. Download the latest BungeeCord jar.
   - Jenkins: https://ci.md-5.net/job/BungeeCord/buildTimeTrend
   - Example direct link: https://hub.spigotmc.org/jenkins/job/BungeeCord/2075/artifact/bootstrap/target/BungeeCord.jar
3. Place `BungeeCord.jar` in the proxy folder.
4. Create a `config.yml` file in the same folder.
5. Create a `plugins` folder for BungeeCord plugins.

## Example `config.yml`

```yaml
listeners:
  - query_port: 25577
    motd: '&1BungeeCord Proxy'
    tab_list: GLOBAL_PING
    query_enabled: false
    host: 0.0.0.0:25577
    max_players: 100
    tab_size: 60
    ping_passthrough: false
    priorities:
      - hub
    fallback_server: hub
servers:
  hub:
    motd: '&2Hub Server'
    address: 127.0.0.1:25565
    restricted: false
  survival:
    motd: '&2Survival Server'
    address: 127.0.0.1:25566
    restricted: false
timeout: 30000
player_limit: 0
query_enabled: false
query_port: 25577
network_compression_threshold: 256
online_mode: true
ip_forward: true
log_commands: false
disabled_commands:
  - disabledcommandhere
connection_throttle: 4000
remote_ping_cache: -1
forge_support: false
prevent_proxy_connections: false
```

## Backend server configuration

On each backend (Spigot/Paper/Bukkit) server:

- Set `online-mode=false` in `server.properties`
- Set `bungeecord: true` in `spigot.yml` or `paper.yml`
- Use unique ports for each backend, for example `25565`, `25566`, `25567`

## Starting the proxy

Run:

```powershell
java -Xms1G -Xmx2G -jar BungeeCord.jar
```

## Notes

- Keep `online_mode: true` on BungeeCord and `online-mode=false` on backend servers.
- Use `ip_forward: true` to preserve player IP addresses.
- Place backend servers behind the proxy with `127.0.0.1` or local network addresses.
- Install BungeeCord-compatible plugins into the proxy `plugins/` folder.

## Recommended next step

Read `../docs/proxy-server.md` for proxy comparisons and use `../setup/proxy/README.md` for additional setup guidance.
