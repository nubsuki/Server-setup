https://wiki.s5gi.com/guides/linux/pterodactyl_and_wings_dockerized For more info

mkdir -p /opt/pterodactyl/wings/config
mkdir -p /opt/pterodactyl/panel/appvar/
mkdir -p /opt/pterodactyl/panel/nginx/
mkdir -p /opt/pterodactyl/panel/logs/


apt install docker-compose -y
cd /opt/pterodactyl/
touch docker-compose.yml


nano docker-compose.yml       (paste the compse file and run)


docker-compose up

After encountering these errors, press Ctrl+C to stop

wings_1     |
wings_1     | Error: Configuration File Not Found
wings_1     |
wings_1     | Wings was not able to locate your configuration file, and therefore is not
wings_1     | able to complete its boot process. Please ensure you have copied your instance
wings_1     | configuration file into the default location below.
wings_1     |
wings_1     | Default Location: /etc/pterodactyl/config.yml
wings_1     |
wings_1     | This is not a bug with this software. Please do not make a bug report
wings_1     | for this issue, it will be closed.
wings_1     |
wings_1     | pterodactyl_wings_1 exited with code 1


docker exec -it pterodactyl_panel_1 php artisan p:user:make     (To make user for pterodactyl panel)


cd /opt/pterodactyl/wings/config
touch config.yml
nano config.yml        (Add node config file)

start wings

Check logs in Portainer. If you get a daemon error in wings, add this in.

cd /opt/pterodactyl/wings/config
nano config.yml 

docker:
  network:
    interfaces:
      v4:
        subnet: 192.54.0.0/16
        gateway: 192.54.0.1



Then start Wings and configure Nginx.