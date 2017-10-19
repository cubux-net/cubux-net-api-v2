Личные данные
=============

.                 | .
----------------- | -------------------------
Базовый адрес API | `/api/v2/sync/user`
Тип данных        | [`Cubux.Sync.UserData`][Cubux.Sync.UserData]

**ВАЖНО:** Требуется авторизация токеном с [разрешением][scopes]:
`UserActivity`.

Персональные данные авторизованного пользователя.

Ниже описаны не совсем стандартные операции, которые поддерживаются в
данном контексте. Стандартные операции см. в
[Контекстах](../02-context.md).


Удаление аккаунта
-----------------

Для удаления пользователем своего аккаунта необходимо отправить удаление
объекта `me`:

    POST /api/v2/sync/user HTTP/1.1
    Host: www.cubux.net
    Authorization: Bearer 617babbbee3cbe4ee28e8c440d405be3c39ea2bd
    Content-Type: application/json; charset=UTF-8
    Content-Length: 134

    {
        "deleted_objects": {
            "me": "01234567-89ab-cdef-0123-456789abcdef"
        }
    }


Создание команды
----------------

Для создания новой команды необходимо отправить запись типа
[`Cubux.MyTeam`][Cubux.MyTeam] в списке объектов `teams`:

    POST /api/v2/sync/user HTTP/1.1
    Host: www.cubux.net
    Authorization: Bearer 617babbbee3cbe4ee28e8c440d405be3c39ea2bd
    Content-Type: application/json; charset=UTF-8
    Content-Length: 297

    {
        "objects": {
            "teams": [
                {
                    "team_uuid": "c811e6cf-12db-4cd6-893f-c43227e1b723",
                    "team": {
                        "title":                 "New team",
                        "default_currency_code": "RUB"
                    }
                }
            ]
        }
    }


[Cubux.MyTeam]: ../../type/user/team.md
[Cubux.Sync.UserData]: ../../type/sync/data-user.md
[scopes]: ../../auth/scopes.md
