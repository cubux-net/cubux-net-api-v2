Тип `Cubux.Sync.ErrorMessage`
=============================

Сообщение об одной ошибке.

Объект со следующими полями:

Поле      | Тип             | Описание
--------- | --------------- | --------
`level`   | `string`        | Уровень ошибки (природа возникновения)
`code`    | `string`        | Код ошибки
`message` | `locale-string` | Человеческое сообщение

Значения полей `level` и `code` см. в [Классификации ошибок][errors].


[errors]: ../../sync/30-errors.md
