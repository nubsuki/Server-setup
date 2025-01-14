
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

**Note:** Ensure the new port is allowed in your firewall settings.

---