- Current Mikrotik CHR 7.15
- Please use docker compose latest
- Additional
```
apt-get update -y
reboot
apt-get install nano perl wget curl -y
```
- Install Docker For Ubuntu 20.4
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
apt-cache policy docker-ce
apt-get install docker-ce -y
systemctl start docker
systemctl enable docker
systemctl status docker
```
-install Docker Compose
```
apt  install docker-compose
```
- Command 

```
mkdir chr
cd chr
wget https://raw.githubusercontent.com/marlirukmana/mikrotik_chr/main/docker-compose.yml
docker compose up -d
```

Please Edit port what you need on docker-compose.yml
```
version: "3"
services:
  chr:
    container_name: mikrotik
    # image: marlirukmana/routeros:latest // only for support kvm-ok cloud
    image: marlirukmana/routeros:nvm
    restart: unless-stopped
    cap_add:
      - NET_ADMIN
    devices:
      - /dev/net/tun
      # - /dev/kvm // only for support kvm-ok cloud
    ports:
      - "80:80"
      - "8291:8291"
      - "8080:51820/udp"
```

Login Winbox/Web Mikrotik
```
username = admin
passowrd =

```

```

Entering Docker containers

To enter a Docker container you can complete the following steps.
Procedure

    Run the following command to list all running Docker containers.

    docker ps

    Locate the name of the rarget container in the NAMES column.
    Start a bash shell by running the following command with the target container name.
    For example,

    docker exec -it <container_name> bash


```

- cek port open
  ```
  sudo ss -ltn
  ```
