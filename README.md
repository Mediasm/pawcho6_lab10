# Laboratorium 10 - PAwChO

## Spis treści
* [Run](#run)
* [Verification](#verification)

## Run

### Create network
```
docker network create lab10net
```

### Create web containers
Web1:
```
docker run -d --name web1_mount \
  --network lab10net \
  -p 8091:80 \
  --mount type=bind,source=C:/sem6/Docker/Lab10/html/web1.html,target=/usr/share/nginx/html/index.html,readonly \
  --mount type=bind,source=C:/sem6/Docker/Lab10/web_mount/lab10_logs/web1,target=/var/log/nginx \
  nginx:latest
```
Web2:
```
docker run -d --name web2_mount \
  --network lab10net \
  -p 8092:80 \
  --mount type=bind,source=C:/sem6/Docker/Lab10/html/web2.html,target=/usr/share/nginx/html/index.html,readonly \
  --mount type=bind,source=C:/sem6/Docker/Lab10/web_mount/lab10_logs/web2,target=/var/log/nginx \
  nginx:latest
```
Web3:
```
docker run -d --name web3_mount \
  --network lab10net \
  -p 8093:80 \
  --mount type=bind,source=C:/sem6/Docker/Lab10/html/web3.html,target=/usr/share/nginx/html/index.html,readonly \
  --mount type=bind,source=C:/sem6/Docker/Lab10/web_mount/lab10_logs/web3,target=/var/log/nginx \
  nginx:latest
```