
```markdown
## Install Docker

To install Docker, run the following command:
```bash
curl https://get.docker.com | bash
```

**Note:** This script automatically detects your system's configuration and installs Docker. Ensure you trust the source before running the script.

---

## Install Portainer

Portainer is a lightweight management UI for Docker. Install it using the following command:

```bash
docker run -d \
  -p 9443:9443 \
  --name portainer \
  --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce:latest
```

---

### Portainer Access Information

- **Portainer Port:** `9443`
- After installation, you can access Portainer by navigating to `https://<your-server-ip>:9443` in your web browser.

---

### Portainer Templates

Enhance Portainer with over 500 preconfigured templates by adding the following template URL:
- **Template URL:** [https://raw.githubusercontent.com/Lissy93/portainer-templates/main/templates.json](https://raw.githubusercontent.com/Lissy93/portainer-templates/main/templates.json)

To add the template:
1. Go to the **"Settings"** section in Portainer.
2. Paste the template URL in the **App Templates** field.
3. Save the settings.

---
