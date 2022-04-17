# Joplin Server
Joplin - an open source note taking and to-do application with synchronization capabilities for Windows, macOS, Linux, Android and iOS. 

* Official repo: https://github.com/laurent22/joplin

## Configuration
Open .env and fill the required parameters:
```
DATA_FOLDER=
APP_BASE_URL=
MAILER_HOST=
MAILER_AUTH_USER=
...
```

## Installation
```
cd joplin
docker-compose pull && docker-compose up -d
```

## Logs
```
docker logs -f joplin-app
```