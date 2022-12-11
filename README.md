**Yatube_api** - это REST API для cоциальной сети Yatube (ссылка на [github](https://github.com/STI-xa/hw05_final])).  Через этот интерфейс смогут работать мобильное приложение или чат-бот; через него же можно передавать данные в любое приложение или на фронтенд.
___
### **Что внутри**:
* Поддерживает все типовые операции CRUD (работает со свсеми модулями Yatube: посты, группы, подписки, комментарии)
* Предоставляет данные в формате JSON
* Аутентификация по Jwt-токену
* Возможность настройки кол-ва числа объектов в запросе и с какого по счёту объекта начать отсчёт
* Возможен поиск по подпискам

___
### **Как запустить проект**:

* Клонировать репозиторий и перейти в него в командной строке:
```
git clone git@github.com:STI-xa/api_final_yatube.git

cd api_final_yatube
```

* Cоздать и активировать виртуальное окружение:
```
python -m venv venv

source venv/Scripts/activate
```

* Установить зависимости из файла requirements.txt:
```
python -m pip install --upgrade pip

pip install -r requirements.txt
```

* Выполнить миграции:
```
python manage.py migrate
```

* Запустить проект:
```
python manage.py runserver
```
___
### **Примеры запросов**:
* GET-запрос возвращает список постов:
```
http://127.0.0.1:8000/api/v1/posts/
```
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
* GET-запрос возвращает комментарии к посту:
```
* http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/
```
```
[
  {
    "id": 0,
    "author": "string",
    "text": "string",
    "created": "2019-08-24T14:15:22Z",
    "post": 0
  }
]
```
* Остальные примеры запросов можно посмотреть по ссылке:

http://127.0.0.1:8000/redoc/
___
### **Стэк технологий**:
* ![image](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)
* ![image](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=green)
* ![image](https://img.shields.io/badge/django%20rest-ff1709?style=for-the-badge&logo=django&logoColor=white)
* ![image](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white)
