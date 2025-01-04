# This tools can be usefull

## Portainer

docker run -d -p 8000:8000 -p 9443:9443 \
  --name portainer --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce:latest

portainer port : 10000


## Webmin

sudo apt install -y software-properties-common apt-transport-https wget

wget -qO - http://www.webmin.com/jcameron-key.asc | sudo apt-key add -

echo "deb http://download.webmin.com/download/repository sarge contrib" | sudo tee /etc/apt/sources.list.d/webmin.list

apt update

sudo apt install webmin -y

webmin port : 10000
