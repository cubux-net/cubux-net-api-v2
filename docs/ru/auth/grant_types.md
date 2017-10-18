Способы предоставления токена доступа
=====================================

Существуют несколько различных вариантов предоставления токена доступа.
Ниже перечислены поддерживаемые способы.

Некоторые имеют дополнительные параметры в запросе токена.


Идентификацие клиента `client_credentials`
------------------------------------------

Данный способ предназначен для довереных клиентов.

Параметры:

Параметр        | По умолчанию      | Описание
--------------- | ----------------- | --------
`client_secret` | **Обязательно**   | Секретный код клиента
`scope`         | _(все доступные)_ | Требуемые разрешения. Можно запрашивать только те, что доступны данному клиенту. По умолчанию используются все доступные.

Пример:

Запрос:

    POST /oauth2/token HTTP/1.1
    Host: www.cubux.net
    Content-Type: application/json; charset=UTF-8
    Content-Length: 114

    {
        "client_id":     "MY_CLIENT_ID",
        "grant_type":    "client_credentials",
        "client_secret": "MY_CLIENT_SECRET",
        "scope":         "SignUp"
    }

Ответ:

    HTTP/1.1 200 OK
    Content-Length: 117
    Content-Type: application/json; charset=UTF-8

    {
        "access_token": "bd21026244e41a126d69f15ea9d1ac76579f69e3",
        "expires_in":   86400,
        "token_type":   "Bearer",
        "scope":        "SignUp"
    }


Идентификацие пользователя `password`
------------------------------------------

Данный способ предназначен для идентификации пользователя его паролем.
Клиенту следует вывести пользователю форму ввода логина и пароля.

Параметры:

Параметр   | По умолчанию      | Описание
---------- | ----------------- | --------
`username` | **Обязательно**   | Логин пользователя
`password` | **Обязательно**   | Пароль пользователя
`scope`    | _(все доступные)_ | Требуемые разрешения. Можно запрашивать только те, что доступны данному клиенту. По умолчанию используются все доступные.

Пример:

Запрос:

    POST /oauth2/token HTTP/1.1
    Host: www.cubux.net
    Content-Type: application/json; charset=UTF-8
    Content-Length: 114

    {
        "client_id":  "MY_CLIENT_ID",
        "grant_type": "password",
        "username":   "User name",
        "password":   "********",
        "scope":      "UserActivity"
    }

Ответ:

    HTTP/1.1 200 OK
    Content-Length: 117
    Content-Type: application/json; charset=UTF-8

    {
        "access_token":  "617babbbee3cbe4ee28e8c440d405be3c39ea2bd",
        "expires_in":    86400,
        "token_type":    "Bearer",
        "scope":         "UserActivity",
        "refresh_token": "790aa43107a8dfde7b1b5c716d72859bcbae89c7"
    }


Обновление токена `refresh_token`
---------------------------------

Данный способ предназначен для получения токена, используя токен
обновления (refresh token) другого токена доступа, полученого ранее.
Новый токен наследует разрешения старого токена.

Параметры:

Параметр        | По умолчанию    | Описание
--------------- | --------------- | --------
`refresh_token` | **Обязательно** | Токен обновления, полученый вместе со старым токеном доступа

Пример:

Запрос:

    POST /oauth2/token HTTP/1.1
    Host: www.cubux.net
    Content-Type: application/json; charset=UTF-8
    Content-Length: 116

    {
        "client_id":     "MY_CLIENT_ID",
        "grant_type":    "refresh_token",
        "refresh_token": "790aa43107a8dfde7b1b5c716d72859bcbae89c7"
    }

Ответ:

    HTTP/1.1 200 OK
    Content-Length: 182
    Content-Type: application/json; charset=UTF-8

    {
        "access_token":  "872bd1c9ba99529256eede2b50c23fac29053384",
        "expires_in":    86400,
        "token_type":    "Bearer",
        "scope":         "UserActivity",
        "refresh_token": "142a4cf7a4596afe4f53d666fed6c350391ea615"
    }
