### Описание проекта

Проект "API для yatube" представляет собой измененную социальную сеть для блогеров Yatube,
для которой теперь доступны запросы к API. Принцип создания интерфейса - REST, переход к API
осуществлен на основе Django REST Framework.

Для чего этот интерфейс может быть полезен:

```
Через этот интерфейс смогут работать мобильное приложение или чат-бот
```

```
Через него же можно будет передавать данные в любое приложение или на фронтенд.
```

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:Amica24/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Примеры запросов к API:

GET-запрос для получения списка всех публикаций на
http://127.0.0.1:8000/api/v1/posts/

Пример ответа при удачном выполнении запроса с пагинацией:

```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}

```

POST-запрос для добавления нового комментария на
http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/

```
{
  "text": "string"
}
```

Пример ответа при удачном выполнении запроса:


```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```

Выше приведены лишь некоторые примеры запросов. Все доступные эндпоинты, примеры
запросов и ответов доступны после запуска сервера по [адресу](http://127.0.0.1:8000/redoc/).
