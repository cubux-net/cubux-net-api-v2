Тип `Cubux.AUser`
=================

Базовый тип для пользователей. Пользователи могут быть
зарегистрированными [`Cubux.User`][Cubux.User] или приглашенными
[`Cubux.Invite`][Cubux.Invite]. И те, и другие имеют единое
"пространство" для UUID.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid` | UUID


[Cubux.Invite]: invite.md
[Cubux.User]: user.md