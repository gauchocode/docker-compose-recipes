# Introducción

Grafana, Promtail y Loki es un estandard para el monitoreo de servidores.
Como complemento, esta receta contiene Netdata con persistencia de datos en influxdb, la cual se puede agregar como data source a Grafana.

## Consideraciones
Para loguearse a Grafana visitar: http://<your_ip>:3000
Loguearse con: admin:admin

Funciona con influxdb:1.8, a partir de influxdb:2.0 no funciona la integración con Grafana.

Cuando se inicia por primera vez, es necesario crear la base en influxdb con el siguiente comando:

```
curl -i -XPOST http://localhost:8086/query --data-urlencode "q=CREATE DATABASE netdata"
```

Para agregarlo como data source:

URL: http://influxdb:8086, o http://user:pass@influxdb:8086
Database: netdata

Importamos el dashboard con ID 10922.

## Comandos
Adentro de cada una de las carpetas ejecutamos:

### Para descargar imágenes
```
docker-compose pull
```

### Para detener y borrar las imagenes actuales (si es que hay alguna corriendo)
```
docker-compose stop && docker-compose rm
```

### Levantamos la nueva instancia
```
docker-compose up -d
```