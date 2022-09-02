# K6
k6 is a modern load testing tool, building on our years of experience in the load and performance testing industry. It provides a clean, approachable scripting API, local and cloud execution, and flexible configuration.

* Official repo: https://github.com/grafana/k6/

## Configuration
No configuration required.

## Installation

### Option 1: with Caddy inside docker stack
```
cd k6
docker-compose pull && docker-compose up -d
```

## Logs
```
docker logs -f k6
```
