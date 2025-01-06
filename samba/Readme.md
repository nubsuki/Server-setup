Update your server: 
sudo apt update
sudo apt upgrade

Create your share director and set permissions 
sudo mkdir /share
sudo chmod 777 /share

Install Samba
sudo apt install samba

Edit the samba confi
sudo nano /etc/samba/smb.conf

# Go to very bottom 
[share]
path = /share
browseable = yes
read only = no
guest ok = no
# if you wanna give root permmition
force user = root
force group = root

Add your samba user
sudo smbpasswd -a [username]
add the password

\\[ip]\share 
# in wondows machine


Set services to auto start on startup
sudo systemctl enable smbd
sudo systemctl enable nmbd
Restart samba services
sudo systemctl restart smbd
sudo systemctl restart nmbd