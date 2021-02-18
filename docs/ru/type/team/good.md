Тип `Cubux.Good`
================

Описание товара в справочнике для списков покупок.

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`       | UUID
`color`       | `color`      | Цвет маркера
`image_uuid` _(устаревшее)_ | `uuid`, NULL | UUID изображения [`Cubux.Image`][Cubux.Image]
`images`      | `Array:uuid` | Список UUID изображений [`Cubux.Image`][Cubux.Image]
`is_favorite` | `boolean`    | Отмечен ли избранным
`is_hidden`   | `boolean`    | Отмечен ли скрытым
`name`        | `string`     | Название


[Cubux.Image]: image.md
