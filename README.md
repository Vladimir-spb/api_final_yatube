# api_yatube описание

REST API для Yatube, учебный проект курса Яндекс.Практикум
Работает с модулями Yatube: постами, комментариями, группами
Предоставляет данные в формате JSON
Аутентификация с помощью JWT-токена

# api_yatube взаимодействие
Регистрация нового пользователя:
api/v1/auth/users/: отправляем username и password 
Получаем токен
api/v1/auth/jwt/create/: в ответ придет "refresh"-нужен для обновления токена и "access"-токен.

Для взаимодействия с ресурсами необходимо направить запросы на следующие эндпоинты:
api/v1/posts/ (GET, POST): получаем список всех постов либо создаём новый пост.
api/v1/posts/{post_id}/ (GET, PUT, PATCH, DELETE): получаем, редактируем или удаляем пост по id в случае если автор поста является лицом отправившим запрос.
api/v1/groups/ (GET): получаем список всех групп.
api/v1/groups/{group_id}/ (GET): получаем информацию о группе по id.
api/v1/posts/{post_id}/comments/ (GET, POST): получаем список всех комментариев поста с id=post_id или создаём новый, указав id поста, который хотим прокомментировать.
api/v1/posts/{post_id}/comments/{comment_id}/ (GET, PUT, PATCH, DELETE): получаем, редактируем или удаляем комментарий по id у поста с id=post_id в случае если автор комментария является лицом отправившим запрос
api/v1/follow/ (GET, POST): GET - получаем список всех подписок, POST - подписываемя на автора переданного в запросе.

# api_yatube запуск проекта dev-режим

Создайте и активируйте виртуальное окружение
Установите зависимости из файла requirements.txt
pip install -r requirements.txt
Выполните миграцию
В папке с файлом manage.py выполните команду:
python manage.py runserver



# api_yatube авторы
Коршак Владимир Юрьевич

