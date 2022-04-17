# Budibase
Budibase is an open-source low-code platform for creating internal apps in minutes. Supports PostgreSQL, MySQL, MSSQL, MongoDB, Rest API, Docker, K8s.

* Official repo: https://github.com/Budibase/budibase

## Configuration
Open .env and fill the required parameters:
```
DATA_FOLDER=
BUDIBASE_PUBLIC_URI=
JWT_SECRET=
ACME_EMAIL=
```

## Installation

### Option 1: with Caddy inside docker stack
```
cd budibase+caddy
docker-compose pull && docker-compose up -d
```

### Option 2: with nginx installed on host
1. Comment "caddy" service part on docker-compose.yml.
2. Run: **docker-compose pull**
3. Run: **docker-compose up -d**
4. Make a copy of nginx.conf on **/etc/nginx/sites-available**
5. Create symbolic link on **/etc/nginx/sites-enabled**
6. Reload nginx: **service nginx reload**
7. Install certbot and run: **certbot --nginx -d vaultwarden.domain.com**

## Logs
```
docker logs -f bbapps
```
