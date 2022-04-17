# n8n with postgres
Free and open fair-code licensed node based Workflow Automation Tool. Easily automate tasks across different services.

* Official repo: https://github.com/n8n-io/n8n

## Installation
n8n default installation use SQLite. This docker-compose recipe use a postgres image to make data persistent.

### Option 1: with traefik inside docker stack
```
cd n8n+postgres
docker-compose pull && docker-compose up -d
```

### Option 2: with nginx installed on host
1. Comment "traefik" service part on docker-compose.yml.
2. Run: **docker-compose pull**
3. Run: **docker-compose up -d**
4. Make a copy of nginx.conf on **/etc/nginx/sites-available**
5. Create symbolic link on **/etc/nginx/sites-enabled**
6. Reload nginx: **service nginx reload**
7. Install certbot and run: **certbot --nginx -d n8n.domain.com**

## Logs
```
docker logs -f n8n
```
