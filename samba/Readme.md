```markdown
# Setting Up a Samba Share on Your Server

### Update Your Server
```bash
sudo apt update
sudo apt upgrade
```

---

### Create Your Share Directory and Set Permissions
```bash
sudo mkdir /share
sudo chmod 777 /share
```

---

### Install Samba
```bash
sudo apt install samba
```

---

### Edit the Samba Configuration
```bash
sudo nano /etc/samba/smb.conf
```

#### Add the Following to the Bottom of the File:
```conf
[share]
path = /share
browseable = yes
read only = no
guest ok = no
# If you want to give root permissions:
force user = root
force group = root
```

---

### Add Your Samba User
```bash
sudo smbpasswd -a [username]
```
- Replace `[username]` with your desired username.  
- Set and confirm the password when prompted.

---

### Access the Share from a Windows Machine
In File Explorer, navigate to:  
```plaintext
\\[ip]\share
```
- Replace `[ip]` with the server's IP address.

---

### Set Samba Services to Auto-Start on Boot
```bash
sudo systemctl enable smbd
sudo systemctl enable nmbd
```

---

### Restart Samba Services
```bash
sudo systemctl restart smbd
sudo systemctl restart nmbd
```
```