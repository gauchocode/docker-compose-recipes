# Appsmith
Low-code framework.

## Instalation
```
docker-compose up -d
```

## Logs
```
docker logs -f appsmith
```
## Update
Appsmith use Watchtower to autoupdate it self, but you cand always update it manually:

```
docker-compose pull && docker-compose up -d --force-recreate appsmith
```
## Export database
```
docker-compose exec appsmith appsmithctl export_db
```
The backup will be exported here:

```
./stacks/data/backup/appsmith-data.archive
```

Backup .env:

```
docker cp appsmith:/appsmith-stacks/configuration/docker.env .
```

## Import database
```
//First, copy the archive file into the container using the following command:
docker cp ./appsmith-data.archive appsmith:/appsmith-stacks/data/restore/

//Second, run the following command to import data from this file:
docker-compose exec appsmith appsmithctl import_db

// Copy a docker.env from the original instance into this one. 
docker cp ./docker.env appsmith:/appsmith-stacks/configuration/

//Restart Appsmith server
docker-compose exec appsmith supervisorctl restart backend
```