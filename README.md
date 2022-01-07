# crowdsec-honeypot
Contains docker-compose and config files for running a crowdsec-based honeypot using various helper containers.

In the same directory as the docker-compose.yml you need to create a .env file with the following variables defined:


BASEPATH= (If you, as I do, have all config- and log files belonging to a container in a special path with a subdir for each container. Ex. /container/appdata/.


SSHD_IP=


CROWDSEC_IP=


(These are rather selfexplanatory but let me explain how networking, docker networking and containers are set up. I have a dedicated DMZ zone on my network where I put various docker containers that are internet exposed. From here there's no connection to other networks on my LAN. Obviously I put these here. I have defined a macvlan docker network called 'macvlan-dmz' corresponding to this subnet with the network adaptor of my DMZ as parent. You will need to adjust CROWDSEC_IP, SSHD_IP and the network name under networks: in docker-compose.yml accordingly.
