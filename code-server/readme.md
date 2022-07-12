# Code Server
Run VS Code on any machine anywhere and access it in the browser.

* Official repo: https://github.com/coder/code-server

## Configuration
Edit .env file to configure domain, ports, and folder where workspace will be stored.

## Installation

### Option 1: with Caddy inside docker stack
```
cd code-server
docker-compose pull && docker-compose up -d
```

### Option 2: with nginx installed on host
1. Comment "caddy" service part on docker-compose.yml.
2. Run: **docker-compose pull**
3. Run: **docker-compose up -d**
4. Make a copy of nginx.conf on **/etc/nginx/sites-available**
5. Create symbolic link on **/etc/nginx/sites-enabled**
6. Reload nginx: **service nginx reload**
7. Install certbot and run: **certbot --nginx -d vscode.domain.com**

## Logs
```
docker logs -f code-server
```
