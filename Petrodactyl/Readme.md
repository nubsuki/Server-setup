```markdown
## Pterodactyl and Wings Docker Setup Guide

This setup guide follows instructions from 5gi. For more details, refer to the [wiki](https://wiki.s5gi.com/guides/linux/pterodactyl_and_wings_dockerized).

### Create Necessary Directories
```bash
mkdir -p /opt/pterodactyl/wings/config
mkdir -p /opt/pterodactyl/panel/appvar/
mkdir -p /opt/pterodactyl/panel/nginx/
mkdir -p /opt/pterodactyl/panel/logs/
```

---

### Install Docker Compose
```bash
apt install docker-compose -y
```

---

### Setup Pterodactyl
```bash
cd /opt/pterodactyl/
touch docker-compose.yml
```

Edit `docker-compose.yml`:
```bash
nano docker-compose.yml
```
(Paste the Docker Compose file and save)

---

### Start Docker Compose
```bash
docker-compose up
```

Alternatively, you can use Portainer to run the containers.

---

### Troubleshooting - Error: "Configuration File Not Found"
If you encounter this error:
```plaintext
Error: Configuration File Not Found
Wings was not able to locate your configuration file...
```

- This means the configuration file is missing. To resolve this:
  1. **Stop the Wings container** (use Ctrl+C).
  2. Create the necessary configuration file:
    ```bash
    cd /opt/pterodactyl/wings/config
    touch config.yml
    nano config.yml
    ```
  3. Add your node configuration to the `config.yml` file.

---

### Creating a User for the Pterodactyl Panel
Before starting Wings, make sure to create a user for Pterodactyl panel:
```bash
docker exec -it pterodactyl_panel_1 php artisan p:user:make
```

---

### Check Logs in Portainer
If you encounter a "daemon error" in Wings, add this configuration to `config.yml`:

```bash
cd /opt/pterodactyl/wings/config
nano config.yml
```

Add the following:
```yaml
docker:
  network:
    interfaces:
      v4:
        subnet: 192.54.0.0/16
        gateway: 192.54.0.1
```

---

### Start Wings
After making these adjustments, start the Wings container in Portainer. Configure Nginx as needed.

```