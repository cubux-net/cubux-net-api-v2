Тип `Cubux.LoanAgent`
=====================

Долговой агент.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`   | UUID
`name`        | `string` | **Обязательно**. Отображаемое имя агента
`icon_uuid`   | `uuid`, NULL | UUID фотографии [`Cubux.Image`][Cubux.Image]
`icon_name`   | `string`     | Имя иконки. Максимум 32 символа.
`sort`        | `integer`    | Порядковый номер для сортировки от `0` до `32767`. Рекомендуется использовать шаг больше 1 для более удобной вставки между соседями. Например: 10, 20, 30, ... или 100, 200, 300, ... Перенумерация соседей при изменении не обязательна, но уместна.
`is_hidden`   | `boolean`    | Агент скрыт


[Cubux.Image]: image.md
