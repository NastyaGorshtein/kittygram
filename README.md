# Kittygram
## Описание проекта

Kittygram — социальная сеть для обмена фотографиями любимых питомцев. Это полностью рабочий проект, который состоит из бэкенд-приложения на Django и фронтенд-приложения на React. Пользователи могут создавать профили, добавлять фотографии своих питомцев, указывать их возраст, цвет и достижения.


Проект развёрнут на сервере и доступен по адресу:

https://kittygram.servehttp.com

---

## Использованные технологии

* Python
* Django
* Django REST Framework
* Djoser
* PostgreSQL
* Docker
* Docker Compose
* Nginx
* React

## Архитектура

Проект состоит из нескольких контейнеров:

* backend — Django приложение
* frontend — React интерфейс
* db — PostgreSQL база данных
* gateway — Nginx

---

# Установка и запуск проекта

## Клонировать репозиторий

```bash
git clone https://github.com/USERNAME/kittygram.git
cd kittygram
```

---

## Создать файл переменных окружения

Создайте файл `.env` на основе шаблона:

```bash
cp .env.example .env
```

## Запуск проекта через Docker

```bash
docker compose -f docker-compose.production.yml up -d
```

После запуска выполните миграции:

```bash
docker compose exec backend python manage.py migrate
```

Соберите статические файлы:

```bash
docker compose exec backend python manage.py collectstatic --noinput
```

---

## Проект будет доступен по адресу

```
http://localhost:9000
```

---

# Примеры API запросов

## Получить список котов

GET

```
/api/cats/
```

Ответ:

```json
[
  {
    "id": 1,
    "name": "Барсик",
    "color": "orange",
    "birth_year": 2018,
    "achievements": [
      "Лучший кот района"
    ]
  }
]
```

---

## Добавить кота

POST

```
/api/cats/
```

Тело запроса:

```json
{
  "name": "Мурзик",
  "color": "white",
  "birth_year": 2020,
  "achievements": ["Самый ласковый в доме"]
}
```

---

## Получить токен пользователя

POST

```
/api/auth/token/login/
```

---

# Автор

-   **Анастасия Горштейн** — [GitHub](https://github.com/NastyaGorshtein)
