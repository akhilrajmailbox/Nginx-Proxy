# Nginx Server (Proxy Server)

## Prerequisites

* We are using `devops-network` docker network for all devops deployment.
* You need at least Docker Engine 17.06.0  and docker-compose 1.18 for this to work.

```bash
docker --version
docker-compose --version
```

## Create custom Docker network before deploying container (If the network is already created then ignore it)

*Note : Make sure that the subnet won't conflict with any other subnets*

```bash
docker network create --driver=bridge --subnet=172.31.0.0/16 devops-network
```

## Deploy nginx as Docker container

```bash
docker-compose -f docker-compose.yml up -d
```


## Working with nginx


* Login to nginx server

```bash
docker exec -it nginx /bin/bash
```

* Restarting nginx

```bash
docker-compose -f docker-compose.yml restart
```

* stopping/starting nginx

```
docker-compose -f docker-compose.yml stop/start
```

* check the logs of nginx server

```bash
docker logs -f nginx
```

