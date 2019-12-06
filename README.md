### List of services

* elasticsearch

* kibana

### Start up

Copy environment file and fill all fields

```bash
cp .env.example .env
```

### Run docker container

```bash
docker-compose up
```

### Init s3 settings

```bash
docker exec elk-local-backup_elasticsearch_1 /start
```

### Set the index (for example - "laravel-2019.12.01") and get it in Kibana

```bash
docker exec elk-local-backup_elasticsearch_1 /restore laravel-2019.12.01
```

### Stop and drop docker containers

```bash
docker-compose down
```