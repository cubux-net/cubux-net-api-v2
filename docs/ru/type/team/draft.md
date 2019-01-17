Тип `Cubux.Draft`
=================

Чек.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`    | UUID
`image`      _(только чтение)_ | `url`, NULL | Ссылка на миниатюру изображения
`image_blob` _(только запись)_ _(устаревшее)_ | `string`, NULL | Код загруженного файла (см. [устаревший способ загрузки файлов][uploads.old])
`photo_uuid` | `uuid` | UUID изображения [`Cubux.Image`][Cubux.Image]
`is_passed`  | `boolean`  | Обработан ли чек
`created_at` _(только чтение)_ | `datetime` | Дата создания чека


[Cubux.Image]: ./image.md
[uploads.old]: ../../sync/10-uploads.old.md
