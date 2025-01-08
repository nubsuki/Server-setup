```markdown
## Fixing Subtitle Issues in Jellyfin

If you experience issues with subtitles not working, add these fonts to Jellyfin. 

### Steps:
1. Download and extract the fonts.  
2. Add the extracted font files to the directory:  
   ```bash
   /mediaserver/fonts
   ```  
   (Change the location if you have modified your Docker setup.)

3. No further configuration is required. Jellyfin will automatically recognize the fonts.

```