# Laravel-on-Docker-compose
Start Laravel Aplication on Docker compose with NGINX , MariaDb , Composer and phpMyAdmin
## Содержание
- [Технологии](#технологии)
- [Установка](#установка)
- [Запуск](#запуск)
- [Database](#database)
- [Другое](#другое)

## Технологии
- PHP 8.3
- Laravel
- MariyaDB
- NGINX
- Composer
- phpMyAdmin
- Docker compose

## Установка

0. Склонировать репозиторий
```sh
$ git clone < https/ssh >
```
1. Переход в дерикторию
```sh
$ cd < name dir >
```
## Запуск
0. Build docker-compose
```sh
$ docker-compose build
```
1. Обновление Composer 
```sh
$ docker-compose run --rm composer create-project --prefer-dist laravel/laravel 
```
2. Задать параметры для BD
```php
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel_user
DB_PASSWORD=laravel_pass
```
3. Запуск контейнера
```sh
$ docker-compose up -d
```
4. Запуск миграций
```sh
$ docker-compose exec app php artisan migrate
```
5. Доступ в приложение 
`http://localhost:8080/`

## Database

0. Использование и управление базы данных в console
```sh
$ docker-compose exec db mariadb -h db -u root -p
```

## Другое 

:)
