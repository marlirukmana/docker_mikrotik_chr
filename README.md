- Current Mikrotik CHR 7.15
- Please use docker compose latest 

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
  routeros:
    container_name: mikrotik
    image: marlirukmana/routeros:latest
    restart: unless-stopped
    cap_add:
      - NET_ADMIN
    devices:
      - /dev/net/tun
      - /dev/kvm
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
