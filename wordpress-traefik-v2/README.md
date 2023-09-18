# Preparation

**Folders and Files**
```
mkdir -p /opt/traefik/{letsencrypt,config,db,wp}
touch /opt/traefik/traefik.log
```

**Proxy Network**
```
docker network create --gateway 192.168.144.1 --subnet 192.168.144.0/24 traefik_proxy
```

# Configuration

**Docker Compose**
*/opt/traefik/docker-compose.yml*

```
docker-compose.yml
```

**Dynamic Configuration**

We used the file provider above to point to our dynamic configuration:
*/opt/traefik/config/dynamic.yml*

```
## Setting up the middleware for redirect to https ##
http:
  middlewares:
    redirect:
      redirectScheme:
        scheme: https
```