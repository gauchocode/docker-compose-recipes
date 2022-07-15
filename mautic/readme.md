# Mautic
Mautic provides free and open source marketing automation software available to everyone. Free email marketing software, lead management and more.

* Official repo: https://github.com/mautic/mautic

## Configuration
Open .env and fill the required parameters.

## Installation

### Option 1: with Apache2 inside docker stack
```
cd mautic
docker-compose pull && docker-compose up -d
```

### Option 2: with nginx installed on host
1. Change Mautic host port on .env file (could be 808 or another open port).
2. Run: **docker-compose pull**
3. Run: **docker-compose up -d**
4. Make a copy of nginx.conf on **/etc/nginx/sites-available**
5. Create symbolic link on **/etc/nginx/sites-enabled**
6. Reload nginx: **service nginx reload**
7. Install certbot and run: **certbot --nginx -d mautic.domain.com**

## Logs
```
docker logs -f mautic
```
