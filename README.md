# Проект Review and API for «YaMDb»

Проект создан в рамках обучения <a href="https://www.djangoproject.com/" target="_blank" rel="noreferrer">Django</a> на факультете Бэкенд. Когорта №9+ Яндекс.Практикум.

Использованы следующие технологии и пакеты:
<p align="left"> 
<a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"> </a>
<a href="https://www.djangoproject.com/" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/django.svg" alt="django" width="40" height="40"/>
</p>

- 🔭 requests
- 🔭 djangorestframework
- 🔭 PyJWT
- 🔭 pytest
- 🔭 pytest-django
- 🔭 pytest-pythonpath
- 🔭 python-dotenv
- 🔭 djangorestframework-simplejwt
- 🔭 django-filter

<h3 align="center">Проект «YaMDb». Описание:</h3>
<p align="left">Проект «YaMDb» собирает отзывы пользователей на различные произведения.</p>
<p align="left">Проект доступен анонимным и аутентифицированным пользователям. 
В данном проекте используется аутентификация по JWT-токену.</p>

Функционал API:

1. Работа с отзывами:

```
- Получение списка всех отзывов. Позволяет получить список всех отзывов.
Права доступа: Доступно без токена;
- Добавление нового отзыва. Позволяет добавить новый отзыв. Пользователь может оставить только один отзыв на произведение.
Права доступа: Аутентифицированные пользователи;
- Получение отзыва по id. Позволяет получить отзыв по id для указанного произведения. Права доступа: Доступно без токена;
- Частичное обновление отзыва по id. Позволяет частичное обновить отзыв по id. Права доступа: Автор отзыва, модератор или администратор.;
- Удаление отзыва по id. Позволяет удалить отзыв по id. 
Права доступа: Автор отзыва, модератор или администратор.
```

2. Работа с комментариями:

```
- Получение списка всех комментариев к отзыву. Позволяет получить список всех комментариев к отзыву. Права доступа: Доступно без токена;
- Добавление комментария. Позволяет добавить новый комментарий для отзыва. Права доступа: Аутентифицированные пользователи;
- Получение комментария к отзыву. Позволяет получить комментарий для отзыва по id. Права доступа: Доступно без токена;
- Частичное обновление комментария к отзыву. Позволяет частично обновить комментарий к отзыву по id. Права доступа: Автор комментария, модератор или администратор;
- Удаление комментария к отзыву. Позволяет удалить комментарий к отзыву по id. Права доступа: Автор комментария, модератор или администратор.
```

3. Работа с категориями:

```
- Получение списка всех категорий. Позволяет получить список всех категорий. Права доступа: Доступно без токена;
- Добавление новой категории. Позволяет создать категорию. Права доступа: Администратор;
- Удаление категории. Позволяет удалить категорию. Права доступа: Администратор.
```

4. Работа с категориями жанров:

```
- Получение списка всех жанров. Позволяет получить список всех жанров. Права доступа: Доступно без токена;
- Добавление жанра. Позволяет добавить жанр. Права доступа: Администратор;
- Удаление жанра. Позволяет удалить жанр. Права доступа: Администратор.

```

5. Работа с произведениями, к которым пишут отзывы (определённый фильм, книга или песенка)

```
- Получение списка всех произведений. Позволяет получить список всех объектов. Права доступа: Доступно без токена;
- Добавление произведения. Позволяет добавить новое произведение. Права доступа: Администратор.
Нельзя добавлять произведения, которые еще не вышли (год выпуска не может быть больше текущего).
При добавлении нового произведения требуется указать уже существующие категорию и жанр;
- Получение информации о произведении. Позволяет получит информацию о произведении. Права доступа: Доступно без токена;
- Частичное обновление информации о произведении. Позволяет обновить информацию о произведении. Права доступа: Администрато;
- Удаление произведения. Позволяет удалить произведение. Права доступа: Администратор.
```

6. Работа с пользователями:

```
- Получение списка всех пользователей. Позволяет получить список всех пользователей. Права доступа: Администратор;
- Добавление пользователя. Позволяет добавить нового пользователя. Права доступа: Администратор.
Поля email и username должны быть уникальными;
- Получение пользователя по username. Позволяет получить пользователя по username. Права доступа: Администратор;
- изменение данных пользователя по username. Позволяет изменить данные пользователя по username.
Права доступа: Администратор. Поля email и username должны быть уникальными.

```

<h3 align="left">Как запустить проект:</h3>

### Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Victor-Manin/api_yamdb.git

cd api_final_yatube
```

### Cоздать и активировать виртуальное окружение:

```
python3 -m venv env

source env/bin/activate

python3 -m pip install --upgrade pip
```

### Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

### Выполнить миграции:

```
python3 manage.py migrate --run-syncdb
```

### В проекте используется технология dotenv, для запуска проекта необходимо: 
создать файл .env в директории, которая содержит файл manage.py. В файле указать SECRET_KEY, 
### пример содержимого файла .env:

```
SECRET_KEY = 'p&l%385148kslhtyn^##a1)ilz@4zqj=rq&agdol^##zgl9(vs'
```

### Запустить проект:

```
python3 manage.py runserver
```

### Примеры запросов и ответов можно найти в документации API
### http://127.0.0.1:8000/redoc/

### Заполнение базы данных из csv файла

Для загрузки данных в пустую базу используйте команду 

```
python3 manage.py import_csv
```

Если необходимо снова загрузить данные из CSV файлов, сначала удалите файо db.sqlite3 для очистки базы данных.
Затем запустите `python3 manage.py migrate --run-syncdb` для создания пустой базы данных с таблицами
