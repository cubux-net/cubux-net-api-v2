Тип `Cubux.TeamInfo`
====================

Данные и настройки команды.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK           | `uuid`      | UUID команды
`title`                 | `string`    | **Обязательно**. Название команды
`default_currency_code` | `string(3)` | Код основной валюты
`time_zone`         | `string`, NULL  | Имя часового пояса (например, `Europe/Moscow`)
`week_start`        | `integer`, NULL | Первый день недели от 1 до 7
