Тип `Cubux.Good`
================

Описание товара в справочнике для списков покупок.

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`       | UUID
`color`       | `color`      | Цвет маркера
`image_uuid`  | `uuid`, NULL | UUID изображения [`Cubux.Image`][Cubux.Image]
`is_favorite` | `boolean`    | Отмечен ли избранным
`name`        | `string`     | Название


[Cubux.Image]: image.md
