
---

## How to Set Up a Linux Server Guide

This is my simple Server setup guide for future reference.

More guids for linux. 

---

### **Services Running in Docker:**

#### **Stream Setup:**
- **Gluten**  
  (with Mullvad OpenVPN/Wireguard) — All containers are in the same network.  
- **qBittorrent**  
- **Homarr**  
- **Sonarr**  
- **Prowlarr**  
- **Radarr**  
- **Jackett**  
- **Bazarr**  
- **Jellyseerr**  

#### **Discord Music Bot:**
- **Ellen**  
  A custom bot that plays music, videos, and supports AI chat.

---

### **Web Servers:**
- **Nginx Proxy Manager**  
  Used to obtain wildcard SSL for my domain.  
- **Nginx**  
  Installed to resolve Webmin-related errors.

---

### **Management Tools:**
- **Webmin**  
  For system management (not in Docker).  
- **Portainer**  
  For easy Docker deployment and configuration.  
- **FileBrowser**  
  Allows easy file browsing.  

---

### **Game Server Management:**
- **Pterodactyl with Wings**  
  Running in Docker for managing game servers.  
- **Petropal**  
  A custom bot that manages servers by shutting them down to free resources and backing up saves to Google Drive.

---

### **Streaming Setup:**
- **Plex**  
- **Jellyfin**  
  (Includes English fonts for proper subtitle rendering).

---

### **SSL Configuration:**
- Standard SSL configuration applied to all services.  
- Special WebSocket SSL configuration for Wings.

---