# Docknode NEAR

## Metrics

* `https://yourdomain.com:9100/metrics`
* `https://yourdomain.com:9102/metrics`


## Prerequisites

* Install git
* Install [docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)


## Install 

1. Clone the repository
```bash
git clone https://github.com/olivbau/docknode-near.git
cd docknode-near
```

2. Configure env variables
```bash
cp .env.example .env

# Generate users passwords for basic auth
docker run --rm caddy:2-alpine caddy hash-password --plaintext 'password'

# Set users and passwords for basic auth
# Set the host
nano .env
```

3. Setup UFW
```bash
ufw allow ssh
ufw deny 3030
ufw enable
```

4. Run
```bash
docker compose pull
docker compose up -d
docker logs -f nearcore --since 1m
docker compose down
```