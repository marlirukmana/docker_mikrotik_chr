- Current Mikrotik CHR 7.15
- Please use docker compose latest 

- Command 

```
mkdir chr
cd chr
wget https://raw.githubusercontent.com/marlirukmana/mikrotik_chr/main/docker-compose.yml
docker compose up -d
```

Please Edit port what you need
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
      - "2222:22"
      - "80:80"
      - "8291:8291"
      - "51820:51820/udp"
```

Login Winbox/Web Mikrotik
```
username = admin
passowrd =

```
