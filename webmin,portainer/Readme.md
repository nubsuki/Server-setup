```markdown
# Useful Tools

## Update and Upgrade System
```bash
apt update && apt upgrade -y
```

---

## Install Docker
```bash
curl https://get.docker.com | bash
```

---

## Portainer
```bash
docker run -d -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```
- **Portainer Port:** `9443`

### 500+ Templates
- Template URL: [https://raw.githubusercontent.com/Lissy93/portainer-templates/main/templates.json](https://raw.githubusercontent.com/Lissy93/portainer-templates/main/templates.json)

---

## Webmin
```bash
sudo apt install -y software-properties-common apt-transport-https wget

wget -qO - http://www.webmin.com/jcameron-key.asc | sudo apt-key add -

echo "deb http://download.webmin.com/download/repository sarge contrib" | sudo tee /etc/apt/sources.list.d/webmin.list

apt update

sudo apt install webmin -y
```
- **Webmin Port:** `10000`
```