# Yamdb

### О проекте

API Yamdb - это бэкэнд часть аггрегатора отзывов на произведения различных категорий: книги, фильмы, музыка. Самих произведений на Yamdb нет, только отзывы с оценками. Пользователи могут просматривать рейтинг произведений в различных категориях и жанрах, читать отзывы к произведениям и оставлять свои комментарии к этим отзывам. Реализована кастомная модель юзер, есть разные роли пользователей - суперюзер, админ, модератор, юзер, аноним. Каждый пользователь обладает собственными правами на создание\удаление пользователей, произведений, отзывов и комментариев.

### Технологии
- Python
- Django
- DRF
- Docker
- PostgreSQL
- nginx
- gunicorn

### Как запустить проект:

Проект запускается в контейнерах Docker

- Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/GlebPogod1n/infra_sp2.git
```

```
cd infra_sp2
```
- Перейти в папку infra:

```
cd infra
```

- В одной директории с файлом docker-compose.yml .env-файл и наполнить его следущими данными:
```
* DB_ENGINE= # указываем, что работаем с postgresql
* DB_NAME= # имя базы данных
* POSTGRES_USER= # логин для подключения к базе данных
* POSTGRES_PASSWORD= # пароль для подключения к БД
* DB_HOST= # название сервиса (контейнера)
* DB_PORT= # порт для подключения к БД
```
- Запустить docker-compose

```
docker-compose up
```
Выполнить по почереди следующие команды:

```
docker-compose exec web python manage.py migrate
```
```
docker-compose exec web python manage.py createsuperuser
```
```
docker-compose exec web python manage.py collectstatic --no-input 
```
```
sudo docker-compose exec web python manage.py loaddata fixtures.json
```

Проект будет доступен локально по адресу:

```
http://localhost/
```


### Заполнение базы данных тестовыми данными:

Из корневой папки проекта перейти в папку api_yamdb:

```
cd api_yamdb
```
Заполнить базу данными из csv файлов:

```
python manage.py fill_db
```

### Примеры обращений к API Yatube:

По адресу http://127.0.0.1:8000/redoc/ подключена документация, в которой
описаны все примеры обращений к API

### Авторы:

Погодин Глеб - [https://github.com/GlebPogod1n](https://github.com/GlebPogod1n)     
Трофимов Руслан - [https://github.com/EdmondKoko](https://github.com/EdmondKoko)   
Чабанный Денис - [https://github.com/DociDog](https://github.com/DociD

### контейнеризация:

Погодин Глеб - [https://github.com/GlebPogod1n](https://github.com/GlebPogod1n)
