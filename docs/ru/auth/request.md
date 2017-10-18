Запрос токена доступа
=====================

Адрес: `/oauth2/token`


Получение токена
----------------

### Запрос

`POST /oauth2/token`

Параметры:

Параметр     | По умолчанию    | Описание
------------ | --------------- | --------
`client_id`  | **Обязательно** | Идентификатор клиента
`grant_type` | **Обязательно** | Способ предоставления токена (см [способы][grant_types])

В завивимости от значения `grant_type` могут быть доступны дополнительные
параметры (в том числе и обязательные).
См. [способы предоставления токена][grant_types].


### Ответ

Поле            | Тип    | Описание
--------------- | ------ | --------
`access_token`  | строка | Токен доступа
`expires_in`    | целое  | Время жизни токен в секундах
`token_type`    | строка | Тип токена
`scope`         | строка | Разрешения, которыми обладает токен
`refresh_token` | строка | Токен обновления (наличие зависит от способа предоставления токена)

### Примеры

#### Получение токена доступа для регистрации пользователя

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


#### Получение токена доступа аутентификации пользователя

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


[scopes]: scopes.md
[grant_types]: grant_types.md
