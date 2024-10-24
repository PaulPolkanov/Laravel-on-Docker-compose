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
0. Создать дерикторию
```sh
$ mkdir < name our dir >
$ cd < name our dir >
```
1. Склонировать репозиторий в данную дерикторию
```sh
$ git clone < https/ssh > .
```
## Запуск
0. Build docker-compose
```sh
$ docker-compose build
```
1. Создание папки для Laravel
```sh
$ mkdir app
```
2. Создать Laravel проект
```sh
$ docker-compose run --rm composer create-project --prefer-dist laravel/laravel .
```
3. Задать параметры для BD
```php
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=root
```
4. Запуск контейнера
```sh
$ docker-compose up -d
```
5. Check Permissions
```sh
$ docker-compose exec app chown -R www-data:www-data /var/www/html/storage /var/www/html/bootstrap/cache
```
6. Запуск миграций
```sh
$ docker-compose exec app php artisan migrate
```
7. Доступ в приложение 
`http://localhost:8090/`

## Database

0. Использование и управление базы данных в console
```sh
$ docker-compose exec db mariadb -h db -u root -p
```

## Другое 

:)
