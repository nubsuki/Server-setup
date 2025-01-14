
```markdown
## How to Update the System

1. Switch to the root user:
   ```bash
   sudo su
   ```

2. Update the package list:
   ```bash
   sudo apt update
   ```

3. Upgrade all installed packages:
   ```bash
   sudo apt upgrade -y
   ```

**Note:** The `-y` flag automatically confirms prompts during the upgrade process. If you'd like to review changes before applying them, omit the `-y`.
```