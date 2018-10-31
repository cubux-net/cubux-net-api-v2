Регистрация
===========

**ВАЖНО:** Требуется авторизация токеном с [разрешением][scopes]: `SignUp`.


### Запрос

`POST /api/v2/sign-up`

В теле запроса передаются следующие поля:

Параметр       | Тип    | По умолчанию    | Описание
-------------- | ------ | --------------- | --------
`mail`         | строка | **Обязательно** | E-mail
`password`     | строка | **Обязательно** | Пароль (минимум 8 символов)
`name`         | строка | **Обязательно** | Имя
`family`       | строка | **Обязательно** | Фамилия
`country_code` | строка | **Обязательно** | Код страны (см [`Cubux.Country`][Cubux.Country])

### Ответ

Результат есть [`Cubux.User`][Cubux.User].

### Пример

Запрос:

    POST /api/v2/sign-up HTTP/1.1
    Host: app.cubux.net
    Authorization: Bearer bd21026244e41a126d69f15ea9d1ac76579f69e3
    Content-Type: application/json; charset=UTF-8
    Content-Length: 97

    {
        "mail":         "foo@example.net",
        "password":     "********",
        "name":         "Foo",
        "family":       "Bar",
        "country_code": "RUS"
    }

Ответ:

    HTTP/1.1 201 Created
    Content-Length: 58
    Content-Type: application/json; charset=UTF-8

    {
        "uuid":     "01234567-89ab-cdef-0123-456789abcdef",
        "username": "Foo Bar"
    }


[Cubux.Country]: ../type/global/country.md
[Cubux.User]: ../type/user/user.md
[scopes]: ../auth/scopes.md
