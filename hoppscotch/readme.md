# Hoppscotch
Open source API development ecosystem.

* Official repo: https://github.com/hoppscotch/hoppscotch

## Configuration
Open and edit .env file.

## Installation

### Option 1: default
```
cd hoppscotch
docker-compose pull && docker-compose up -d
```

### Option 2: with nginx installed on host
1. Run: **docker-compose pull**
2. Run: **docker-compose up -d**
3. Make a copy of nginx.conf on **/etc/nginx/sites-available**
4. Create symbolic link on **/etc/nginx/sites-enabled**
5. Reload nginx: **service nginx reload**
6. Install certbot and run: **certbot --nginx -d hoppscotch.domain.com**

## Logs
```
docker logs -f hoppscotch
```
