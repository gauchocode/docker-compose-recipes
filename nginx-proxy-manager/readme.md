# Nginx Proxy Manager
Pre-built docker image that enables you to easily forward to your websites running at home or otherwise, including free SSL, without having to know too much about Nginx or Letsencrypt.

* Official repo: https://github.com/NginxProxyManager/nginx-proxy-manager

## Installation

### Option 1: without proxy
```
cd nginx-proxy-manager
docker-compose pull && docker-compose up -d
```

### Option 2: with nginx installed on host
1. Run: **docker-compose pull**
2. Run: **docker-compose up -d**
3. Make a copy of nginx.conf on **/etc/nginx/sites-available**
4. Create symbolic link on **/etc/nginx/sites-enabled**
5. Reload nginx: **service nginx reload**
6. Install certbot and run: **certbot --nginx -d nginx.domain.com**

If you change nginx-proxy-manager port, you need to change it on nginx.conf too.

### Log in to the Admin UI
When your docker container is running, connect to it on port 81 for the admin interface. 
Sometimes this can take a little bit because of the entropy of keys.

http://127.0.0.1:81

Default Admin User:

Email:    admin@example.com
Password: changeme

## Logs
```
docker logs -f nginx-proxy-manager
```
