to make your laptop can close lid (server will work after closing display)

Go to 

nano /etc/systemd/logind.conf

Chage these settings,

HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
HandleLidSwitchDocked=ignore
LidSwitchIgnoreInhibited=no