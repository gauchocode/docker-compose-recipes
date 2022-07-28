# Typebot
Typebot is an open-source project that allows you to create conversational apps/forms (Lead qualification, Product launch, User onboarding, Customer support), embed them anywhere on your web/mobile apps, and collect results in real-time.

* Official repo: https://github.com/baptisteArno/typebot.io

## Configuration
Open and edit .env file.

## Installation

### Option 1: default
```
cd typebot
docker-compose pull && docker-compose up -d
```

### Option 2: with nginx installed on host
1. Run: **docker-compose pull**
2. Run: **docker-compose up -d**
3. Make a copy of nginx.conf on **/etc/nginx/sites-available**
4. Create symbolic link on **/etc/nginx/sites-enabled**
5. Reload nginx: **service nginx reload**
6. Install certbot and run: **certbot --nginx -d typebot.domain.com,typebot-builder.domain.com**

## Logs
```
docker logs -f typebot-viewer
docker logs -f typebot-builder
```
