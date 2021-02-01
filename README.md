# Project full-stack

## Set up

### Backend

```shell
cd slim-backend;
composer install
```

### Frontend

```shell
cd ci4-frontend
composer install
chmod o+rw writable/{cache,logs} -v
npm install
```

### General

Separated containers:

```shell
docker run \
-it \
--name fusionote-slim4 \
-p 2122:2122 \
--mount type=bind,source=$(pwd)/slim-backend,target=/srv/www/vhosts/slim.starter \
veritus4/lamp-docker:latest
```

```shell
docker run \
-it \
--name fusionote-ci4 \
-p 2124:2121 \
--mount type=bind,source=$(pwd)/ci4-frontend,target=/srv/www/vhosts/ci4.starter \
veritus4/lamp-docker:latest
```

### Specific

Composed architecture:

```shell
docker-compose up -d
```

