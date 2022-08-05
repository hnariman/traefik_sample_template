# Minimalist Traefik ( just works on my machine )

Traefik is used as load balanceer & API Gateway 

There are two potions of configuraiton: 
- within docker-compose.yml file
- by uncommenting attaching config directory as docker volume

## NGINX as server
NGINX is being used as a sample statis server

nginx.conf is ignored, we only attach/replace static default (html) files through docker volumes

## Routing
Routing is done through docker.layers (see in docker-compose.yml), such approact allows us to update routing without restarting containers, which is is IMHO the Selling Point of Traefik on the first place

## Requirements:
- Docker
- docker-compose

## How To:
to start: 
```bash
$ docker-compose up -d --remove-orphans
```

to stop & remove volumes: 
```bash
$ docker-compose down -v
```

test dashboard:
```bash
$ curl -XGET http://localhost:8080/dashboard
```

test web.server:
```bash
$ curl -XGET http://web.localhost
```

![image](https://user-images.githubusercontent.com/31799546/183222869-db488e81-41a6-4eaa-b6bc-7149c556387d.png)
