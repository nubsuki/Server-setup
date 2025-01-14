
```markdown
## How to Change the SSH Port Number

1. Switch to the root user:
   ```bash
   sudo su
   ```

2. Open the SSH configuration file:
   ```bash
   nano /etc/ssh/sshd_config
   ```

3. Locate the line containing `#Port 22`. Uncomment it by removing the `#` and change the port number to your desired value (e.g., `2222`):
   ```
   Port 2222
   ```

4. Save the file and exit Nano:
   - Press `Ctrl + O` to save.
   - Press `Enter` to confirm.
   - Press `Ctrl + X` to exit.

5. Restart the SSH service to apply the changes:
   ```bash
   systemctl restart sshd
   ```

6. Verify that the new port is active:
   ```bash
   netstat -tuln | grep 2222
   ```

---

### Allow SSH Access to All Local Devices

To allow all devices in your local network to access the SSH server:

1. Use the following command:
   ```bash
   sudo ufw allow from 192.168.1.0/24
   ```
   Replace `192.168.1.0/24` with your network's IP range.

---

### Remove a Port or Rule in UFW

1. Check the current UFW rules:
   ```bash
   sudo ufw status numbered
   ```

2. Delete the rule by its number:
   ```bash
   sudo ufw delete X
   ```
   Replace `X` with the rule number.

   For example, to delete rule #3:
   ```bash
   sudo ufw delete 3
   ```

3. Verify the updated UFW rules:
   ```bash
   sudo ufw status
   ```

---

**Note:** Ensure that any changes to UFW (firewall) rules don’t unintentionally block legitimate traffic. Always test connectivity after making changes.
```