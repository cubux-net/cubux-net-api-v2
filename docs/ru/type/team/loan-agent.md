Тип `Cubux.LoanAgent`
=====================

Долговой агент.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`   | UUID
`name`        | `string` | **Обязательно**. Отображаемое имя агента
`icon_uuid`   | `uuid`, NULL | UUID фотографии [`Cubux.Image`][Cubux.Image]


[Cubux.Image]: image.md
