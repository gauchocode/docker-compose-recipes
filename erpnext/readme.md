# ERPNext
Free and Open Source Enterprise Resource Planning (ERP).

* Official repo: https://github.com/frappe/frappe_docker

## Configuration
Open .env and fill the required parameters:
```
LETSENCRYPT_EMAIL=
SITE_NAME=
SITES=
```

## Installation
```
cd erpnext
docker-compose pull && docker-compose --project-name 'PROJECT_NAME' restart
```

## Logs
```
docker logs -f erpnext
```

### Backup
```
docker run -e "SITES=erp.broobe.com" -e "WITH_FILES=1" -v erpbroobecom_sites-vol:/home/frappe/frappe-bench/sites --network erpbroobecom_default frappe/erpnext-worker:edge backup
```

### Restore
```
docker run -e "MYSQL_ROOT_PASSWORD=admin" -e "BUCKET_NAME=backups" -e "BUCKET_DIR=frappe-bench" -v custom_frappe_docker_sites-vol:/home/frappe/frappe-bench/sites -v custom_frappe_docker_sites-vol:/home/frappe/backups --network custom_frappe_docker_default custom-app-erpnext-worker:v13 restore-backup
```

## Fix to common problems

### The system is being updated
Edit config file with the command:
```
docker run -it -v erpbroobecom_sites-vol:/sites alpine vi /sites/common_site_config.json
```
Remove this line:
```
"maintenance mode":1
```
Restart docker instance:
```
docker-compose --project-name erp.broobe.com restart
```
Remove cache:
```
docker run -v erpbroobecom_sites-vol:/home/frappe/frappe-bench/sites --network erpbroobecom_default --user frappe frappe/frappe-worker:edge bench --site erp.broobe.com clear-cache
```