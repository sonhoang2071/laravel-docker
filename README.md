# docker-laravel 🐳

<p align="center">
    <img src="https://user-images.githubusercontent.com/35098175/145682384-0f531ede-96e0-44c3-a35e-32494bd9af42.png" alt="docker-laravel">
</p>

## Introduction

Build a simple laravel development environment with docker-compose. Compatible with Windows(WSL2), macOS(M1) and Linux.

## Usage

### Create an initial Laravel project

1. Click [Use this template](https://github.com/ucan-lab/docker-laravel/generate)
2. Git clone & change directory
3. Execute the following command

```bash
$ make create-project

# or...

$ mkdir -p src
$ cp .env.example .env
$ docker compose build
$ docker compose up -d
$ docker compose exec app composer create-project --prefer-dist laravel/laravel .
$ docker compose exec app php artisan key:generate
$ docker compose exec app php artisan storage:link
$ docker compose exec app chmod -R 777 storage bootstrap/cache
$ docker compose exec app php artisan migrate
```

http://localhost

## Container structures

```bash
├── app
├── web
└── db
```

### app container

-   Base image
    -   [php](https://hub.docker.com/_/php):8.3-fpm-bullseye
    -   [composer](https://hub.docker.com/_/composer):2.6

### web container

-   Base image
    -   [nginx](https://hub.docker.com/_/nginx):1.25

### db container

-   Base image
    -   [mysql/mysql-server](https://hub.docker.com/r/mysql/mysql-server):8.0

### mailpit container

-   Base image
    -   [axllent/mailpit](https://hub.docker.com/r/axllent/mailpit)
