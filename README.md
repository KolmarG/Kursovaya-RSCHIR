# Авторизация
##### Регистрация
```url
http://127.0.0.1:8000/api/users/register/
```

```json
{
    "username": "testuser2",
    "email": "test2@example.com",
    "password": "userpassword1234",
    "bio": "Hello, world!"
}
```
##### Вход
```url
http://127.0.0.1:8000/api/users/login/
```

```json
{
    "username": "testuser",
    "password": "userpassword123"
}
```

##### Выход
```url
http://127.0.0.1:8000/api/users/logout/
```

```json
надо добавить строку в заголовок:
X-CSRFToken : взять из куки после авторизации.
```
# Сам форум

##### Создать
```url
http://127.0.0.1:8000/api/forums/
```

```json
{
    "name": "Tech Community",
    "description": "A forum for tech enthusiasts."
}
```
##### GET
```URL
http://127.0.0.1:8000/api/forums/2
```

```URL
http://127.0.0.1:8000/api/forums/
```

##### PATCH

```URL
http://127.0.0.1:8000/api/forums/2/
```

```JSON
{
    "name": "Tech Community2"
}
```

##### PUT
```URL
http://127.0.0.1:8000/api/forums/2/
```

```JSON
{
    "name": "Tech Community",
    "description": "A forum for tech enthusiasts."
}
```

##### DELETE
```URL
http://127.0.0.1:8000/api/forums/2/
```
# Посты
тоже самое
```URL
http://127.0.0.1:8000/api/posts/
```

```json
{
    "forum": 1,
    "author": 1,
    "title": "How to set up Django?",
    "content": "Can someone guide me on how to start with Django?"
}
```
# Рейтинги
Тоже самое
```urls
http://127.0.0.1:8000/api/ratings/
```

```url
{
    "user": 1,
    "post": 1,
    "score": 1
}
```

# Глобальные рейтинги
1. **GET-запрос** на получение глобального рейтинга пользователя с `pk=1`:

```bash
GET /users/global-rating/1/
```

**Ответ:**

```json
{
    "user": 1,
    "rating": 12
}
```

2. **POST-запрос** на создание глобального рейтинга для пользователя с `pk=1`:

```bash
POST /users/global-rating/1/
```

**Ответ:**

```json
{
    "user": 1,
    "rating": 0
}
```

3. **PUT-запрос** на обновление глобального рейтинга пользователя с `pk=1`:

```bash
PUT /users/global-rating/1/

{
    "rating": 15
}
```

**Ответ:**

```json
{
    "user": 1,
    "rating": 15
}
```

4. **DELETE-запрос** на удаление глобального рейтинга пользователя с `pk=1`:

```bash
DELETE /users/global-rating/1/
Authorization: Bearer <access_token>
```

**Ответ:**

```json
{
    "message": "Global rating deleted"
}
```
