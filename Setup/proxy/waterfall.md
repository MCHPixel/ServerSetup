# Waterfall Proxy Setup

Waterfall is a fork of BungeeCord that improves stability and performance, but it is no longer actively maintained.

## Requirements

- Java 17 or newer
- Backend servers running Bukkit/Spigot/Paper
- Port `25577` available for the proxy

## Setup steps

1. Create a proxy folder.
   - Example: `C:\Minecraft\proxy`
2. Download Waterfall.
   - Official Jenkins or community mirrors may still host builds.
3. Place `Waterfall.jar` in the proxy folder.
4. Create a `config.yml` file in the same folder.
5. Create a `plugins` folder for Waterfall plugins.

## Example `config.yml`

```yaml
listeners:
  - query_port: 25577
    motd: '&1Waterfall Proxy'
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
connection_throttle: 4000
remote_ping_cache: -1
forge_support: false
prevent_proxy_connections: false
```

## Backend server configuration

On each backend server:

- Set `online-mode=false` in `server.properties`
- Set `bungeecord: true` in `spigot.yml` or `paper.yml`
- Use unique backend ports such as `25565`, `25566`, `25567`

## Starting Waterfall

Run:

```powershell
java -Xms1G -Xmx2G -jar Waterfall.jar
```

## Notes

- Waterfall is no longer actively maintained, so prefer BungeeCord or Velocity for new networks.
- Use Waterfall only if you need compatibility with older BungeeCord plugins.
- Keep backend servers behind the proxy and do not let players connect directly to them.

## Recommended next step

Read `../docs/proxy-server.md` for proxy comparisons and use `../setup/proxy/README.md` for setup guidance.
