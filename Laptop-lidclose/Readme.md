```markdown
### Prevent Laptop from Sleeping When Lid is Closed (Keep Server Running)

To ensure your server continues running when the laptop lid is closed, follow these steps:

1. **Edit the logind.conf File**  
   Open the file in a text editor:
   ```bash
   sudo nano /etc/systemd/logind.conf
   ```

2. **Modify the Following Settings:**
   - `HandleLidSwitch=ignore`
   - `HandleLidSwitchExternalPower=ignore`
   - `HandleLidSwitchDocked=ignore`
   - `LidSwitchIgnoreInhibited=no`

   The configuration should look like this:
   ```bash
   HandleLidSwitch=ignore
   HandleLidSwitchExternalPower=ignore
   HandleLidSwitchDocked=ignore
   LidSwitchIgnoreInhibited=no
   ```

3. **Save and Exit**  
   Press `Ctrl+X` to save and exit the editor, then confirm the changes.

4. **Restart the systemd service**  
   ```bash
   sudo systemctl restart systemd-logind
   ```

After these changes, your laptop will not suspend or shut down when the lid is closed, allowing the server to continue running.
```