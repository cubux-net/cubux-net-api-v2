API Синхронизации cubux.net v2
==============================

**Предупреждение:** _API v2 ещё не выпущено в релиз, доступно только на
**тестовом** сервере, и может быть ещё недостаточно стабильным_.

API синхронизации предназначено для "толстого клиента" - т.е. для
клиента, который хранит у себя снапшот базы данных (разумеется, не всей
базы с сервера, а только необходимые наборы данных).


Обзор
-----

API удовлетворяет принципам REST.

Относительные адреса АПИ запросов в данной документации даны
относительно _Базовый адрес API_. В таблице ниже также приведены адреса
серверов для хранения файлов пользователей.

Сервер ↓   \   Окружение →     | Рабочий                   | Тестовый
------------------------------ | ------------------------- | --------
Базовый адрес API              | `https://www.cubux.net/`  | `https://test.cubux.net/`
Хранилище файлов пользователей | `https://file.cubux.net/` | `https://filetest.cubux.net/`

Данные в теле запросов и ответов передаются в JSON, если явно не
документирован иной формат.

HTTP запросы используют HTTP кеширование, где это допустимо.


Содержание
----------

*   [Аутентификация](auth/README.md)
    *   [Запрос токена доступа](auth/request.md)
    *   [Разрешения (scope)](auth/scopes.md)
    *   [Способы предоставления токена доступа](auth/grant_types.md)
*   [Пользователи](user/README.md)
    *   [Регистрация](user/sign-up.md)
    *   [Сброс пароля](user/password-reset.md)
*   [Типы данных](type/README.md)