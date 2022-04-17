# Grafana, Promtail, Loki & Netdata
Grafana is an open source data visualization platform which is primarily used for displaying metrics dashboards. It can aggregate, query, and display data from multiple sources such as Graphite, Prometheus, or MySQL.

## Configuration
No configuration required.

## Installation
```
cd grafana+promtail+loki+netdata
docker-compose pull && docker-compose up -d
```

## Considerations
* Grafana works with influxdb:1.8, dont works properly with influxdb:2.0+
* Grafana login: http://<your_ip>:3000
* Default first login: admin:admin
* We will neet to create a database in influxdb with the next command:
    ```
    curl -i -XPOST http://localhost:8086/query --data-urlencode "q=CREATE DATABASE netdata"
    ```
* And add it as datasource:
URL: http://influxdb:8086, or http://user:pass@influxdb:8086
Database: netdata
Then you can add the dashboard with ID: 10922