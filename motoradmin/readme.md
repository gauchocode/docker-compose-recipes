# Motor Admin
Deploy a no-code admin panel for any application in less than a minute. Search, create, update, and delete data entries, create custom actions, and build reports.

* Official repo: https://github.com/motor-admin/motor-admin

## Installation

1. Crate a key base with the command: `openssl rand -hex 64`
2. Update docker-compose.yml to add the new key on SECRET_KEY_BASE var.

### Option 1: without proxy
```
cd motoradmin
docker-compose pull && docker-compose up -d
```

### Option 2: with nginx installed on host
1. Run: **docker-compose pull**
2. Run: **docker-compose up -d**
3. Make a copy of nginx.conf on **/etc/nginx/sites-available**
4. Create symbolic link on **/etc/nginx/sites-enabled**
5. Reload nginx: **service nginx reload**
6. Install certbot and run: **certbot --nginx -d motoradmin.domain.com**

If you change motoradmin port, you need to change it on nginx.conf too.

## Logs
```
docker logs -f motoradmin
```
