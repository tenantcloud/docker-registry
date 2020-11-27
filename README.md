# Own Docker Registry

## Install

```bash
git clone https://github.com/tenantcloud/docker-registry.git
cd docker-registry
cp .env.example .env
```

Edit your `.env` file and up your own docker registry

```bash
docker-compose up -d
```

## Proxy your registry

### Over NGINX

Copy `config/nginx-docker-registry.conf` to your nginx folder and change variables
to yours. Restart NGINX.

## Using

Push your images to docker registry

```bash
docker image tag alpine:edge 127.0.0.1:5000/alpine:edge
# Push to registry
docker push 127.0.0.1:5000/alpine:edge
# Pull from registry
docker pull 127.0.0.1:5000/alpine:edge
```
