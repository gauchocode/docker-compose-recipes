# Penpot
Penpot is the first Open Source design and prototyping platform meant for cross-domain teams.

* Official repo: https://github.com/penpot/penpot

## Configuration
Open .env and fill the required parameters:
```
DATA_FOLDER=
PENPOT_PUBLIC_URI=
ACME_EMAIL=
PENPOT_SMTP_ENABLED=
```

## Installation

### Option 1: with Caddy inside docker stack
```
cd penpot+caddy
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
docker logs -f penpot
```
