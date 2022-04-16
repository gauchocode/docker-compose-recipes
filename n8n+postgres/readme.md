# n8n with postgres
n8n default installation is with SQLite. This use a postgres image to make data persistent.

## Installation

### Option 1: with Traefik inside docker stack
1- Run docker-compose pull
2- Run docker-compose up -d

### Option 2: with nginx installed on host
1- Comment "traefik" service parte on docker-compose.yml.
2- Run docker-compose pull
3- Run docker-compose up -d
4- Make a copy of nginx.conf on /etc/nginx/sites-available
5- Create symbolic link on /etc/nginx/sites-enabled
6- Reload nginx service
7- Install certbot and run: certbot --nginx -d n8n.domain.com