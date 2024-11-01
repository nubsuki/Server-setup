
---

## VPS Setup

This is my simple VPS setup guide for future reference.

### Services Running in Docker:
- **Gluten** (with Mullvad OpenVPN) — All containers are in the same network.
- **qBittorrent**
- **Homarr**
- **Sonarr**
- **Prowlarr**
- **Radarr**
- **Jackett**
- **Bazarr**
- **Jellyseerr**
- **Ellen** — A custom bot that plays music and videos and has AI chat

### Web Servers:
- **Nginx Proxy Manager** — Used to obtain wildcard SSL for my domain.
- **Nginx** — Installed and fix some Webmin errors I ran into.

### Management Tools:
- **Webmin** — For system management (not in Docker).
- **Portainer** — For easy Docker deployment and configuration.

### Game Server Management:
- **Pterodactyl** with Wings — Running in Docker.
- **Petropal** — A custom bot to manage servers, shutting them down to free resources and backing up saves to Google Drive.

### Streaming Setup:
- **Plex**
- **Jellyfin**

### SSL:
- Standard SSL configuration for all services.
- Specific WebSocket SSL configuration for Wings.

---