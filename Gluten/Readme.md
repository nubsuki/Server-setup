```markdown
### For More Information

Visit the following site for additional setup details:  
[https://github.com/qdm12/gluetun-wiki/tree/main/setup/providers](https://github.com/qdm12/gluetun-wiki/tree/main/setup/providers)

---

### This Setup Includes:

- **qBittorrent**  
- **Homarr**  
- **Sonarr**  
- **Prowlarr**  
- **Radarr** 
- **Jellyseerr**  
- **tachidesk**  
- **Bazarr**  
- **Jellyseerr** 
- **flaresolverr** 

### Change permission for tachidesk:
sudo ls -lah /mediaserver/tachidesk

sudo chown -R 1000:1000 /mediaserver/tachidesk

sudo chmod -R 755 /mediaserver/tachidesk

All of these services are running together, configured within a VPN setup.
```