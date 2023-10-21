# Kittygram 

## Описание проекта:
Kittygram — социальная сеть для обмена фотографиями любимых питомцев. Проект состоит из бэкенд-приложения на Django и фронтенд-приложения на React.

## Как запустить локально:

### Клонируйте репозиторий и перейдите в него:   
```sh/bash
git@github.com:Anastasia289/kittygram_final.git
cd kittygram_final
```
   
### Cоздайте файл .env, заполните по образцу .env.example    


### Запустите docker-compose.yml, выполните миграции и соберите статику
```sh/bash
docker compose up

docker compose exec backend python manage.py migrate
docker compose exec backend python manage.py collectstatic
docker compose exec backend cp -r /app/backend_static/. /backend_static/static/

```

А еще проект можно задеплоить на сервер. Те, кто захочет им поделиться с пользователями в интернете, уже умные и сильно продвинутые, а потому не нуждаются в дополнительных инструкциях (установить докер, настроить внешний nginx, создать директорию kittygram и перейти в нее, создать там файл .env с нужными переменными, скопироьвать и запустить docker-compose.production.yml, выполнить миграции, собрать статику)...



### Технологии
Python 3.9
Docker
PostgreSQL
Django
Gunicorn
Nginx
JS

[Kittygram](https://procrastination2.hopto.org/) 


![example workflow](https://github.com/github/docs/actions/workflows/main.yml/badge.svg)

[![Main Kittygram workflow](https://github.com/Anastasia289/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/Anastasia289/kittygram_final/actions/workflows/main.yml)

## Автор: 
   
Анастасия Богданова   
bogdanovanastja@yandex.ru  
@lyckkkyday
