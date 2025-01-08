```markdown
### Updating Docker Compose Containers

1. Navigate to the directory where your `docker-compose.yml` file is located:
   ```bash
   cd /path/to/your/docker-compose.yml
   ```

2. Pull the latest versions of the images:
   ```bash
   docker-compose pull
   ```

3. Stop and remove the existing containers:
   ```bash
   docker-compose down
   ```

4. Start the updated containers in detached mode:
   ```bash
   docker-compose up -d
   ```

And you're done!
```