# Kittygram 

## Описание проекта:
Kittygram — социальная сеть для обмена фотографиями любимых питомцев. Проект состоит из бэкенд-приложения на Django и фронтенд-приложения на React.

## Инструкция по запуску:

### Клонируйте репозиторий:   
```sh/bash
git@github.com:Anastasia289/kittygram_final.git
```
   
### Cоздайте файл .env, заполните по образцу .env.example    


### Создайте Docker-образы
- Выполните команды:  
```sh/bash
cd frontend
docker build -t YOUR_USERNAME/kittygram_frontend .
cd ../backend
docker build -t YOUR_USERNAME/kittygram_backend .
cd ../nginx
docker build -t YOUR_USERNAME/kittygram_gateway . 
cd ..
```

### Загрузите созданные образы на Docker-хаб
- Выполните команды:  
```sh/bash
docker push YOUR_USERNAME/kittygram_backend:latest 
docker push YOUR_USERNAME/kittygram_frontend:latest
docker push YOUR_USERNAME/kittygram_gateway:latest

```

### Если на сервере не установлен Docker Compose, установите его

```sh/bash
sudo apt update
sudo apt install curl
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo apt install docker-compose

```

### На сервере создайте директорию kittygram, скопируйте туда файлы docker-compose.production.yml и .env 

### Обновите настройки Nginx.


### Запустите Docker Compose
```sh/bash
sudo docker-compose -f /home/YOUR_USERNAME/kittygram/docker-compose.production.yml up -d

```

### Соберите статику и выполните миграции

```sh/bash
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/backend_static/. /static/

```


## Автор: 
   
Анастасия Богданова   
bogdanovanastja@yandex.ru  
@lyckkkyday