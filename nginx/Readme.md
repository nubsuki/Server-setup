```markdown
### How to Install Nginx on Your System

1. **Update Package Lists**  
   ```bash
   sudo apt update
   ```

2. **Install Nginx**  
   ```bash
   sudo apt install nginx
   ```

3. **Start Nginx**  
   ```bash
   sudo systemctl start nginx
   ```

---

### Webmin Error Fix (Forgot to Install Dependency)

If you encounter errors in Webmin, install the missing dependency:

1. **Update Package Lists Again**  
   ```bash
   sudo apt update
   ```

2. **Install the Required Perl Module**  
   ```bash
   sudo apt install libhtml-parser-perl
   ```

3. **Restart Webmin**  
   ```bash
   sudo systemctl restart webmin
   ```

This should fix the issue and allow Webmin to function correctly.
```