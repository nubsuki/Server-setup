
```markdown
## How to Install Webmin

1. Install necessary dependencies:
   ```bash
   sudo apt install -y software-properties-common apt-transport-https wget
   ```

2. Add the Webmin GPG key:
   ```bash
   wget -qO - http://www.webmin.com/jcameron-key.asc | sudo apt-key add -
   ```

3. Add the Webmin repository to your sources list:
   ```bash
   echo "deb http://download.webmin.com/download/repository sarge contrib" | sudo tee /etc/apt/sources.list.d/webmin.list
   ```

4. Update your package list:
   ```bash
   sudo apt update
   ```

5. Install Webmin:
   ```bash
   sudo apt install webmin -y
   ```

---

### Webmin Access Information

- **Webmin Port:** `10000`
- After installation, you can access Webmin by navigating to `https://<your-server-ip>:10000` in your web browser.

**Note:** Make sure port `10000` is open in your firewall. You can allow it using:
```bash
sudo ufw allow 10000
```

**Tip:** For added security, consider limiting access to Webmin to trusted IPs only.
```
