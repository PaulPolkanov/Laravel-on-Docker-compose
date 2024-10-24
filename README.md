# Laravel-on-Docker-compose
Start Laravel Aplication on Docker compose with NGINX , MariaDb , Composer and phpMyAdmin
## Содержание
- [Технологии](#технологии)
- [Установка и запуск](#установка)
- [Другое](#другое)

## Технологии
- PHP 8.3
- Laravel 11
- MariyaDB
- NGINX
- Composer
- phpMyAdmin

## Установка

0. Склонировать репозиторий
```sh
$ git clone < https/ssh >
```
1. Переход в дерикторию
```sh
$ cd adat-laravel
```
2. Переход на ветку develop
```sh
$ git checkout develop
```

3. Build docker-compose
```sh
$ docker-compose build
```
4. Set Up Environment File
Перейти в app и скопировать .env.example и в .env
```sh
$ cd app/
$ cp .env.example .env
$ cd ..
```
5. Задать параметры для BD
```php
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_MASTERBASE=aftermarketdata
DB_DATABASE=laravel
DB_USERNAME=you_user
DB_PASSWORD=secret
```
6. Запуск контейнера
```sh
$ docker-compose up -d
```
7. Обновление Composer 
```sh
$ docker-compose run --rm composer update
```
8. Генерируем ключ для Laravel Application
```sh
$ docker-compose exec app php artisan key:generate
```
8. Запуск миграций
```sh
$ docker-compose exec app php artisan migrate
```
9. Доступ в приложение 
`http://localhost:8080/`


## Другое 

:)
