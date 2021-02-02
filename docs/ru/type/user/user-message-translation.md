Тип `Cubux.UserMessageTranslation`
==================================

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid` | UUID
`language_code` | `string` | Язык
`body` | `string` | HTML контент
`images` | `Array:`[`Cubux.AttachImageOld`][Cubux.AttachImageOld] | Только растровые изображения для обратной совместимости
`images_with_vector` | `Array:`[`Cubux.AttachImageOld`][Cubux.AttachImageOld] | Все изображения. См. поле `is_vector`.


[Cubux.AttachImageOld]: ../upload/attach-image-old.md
