Тип `Cubux.Me`
==============

Данные профайла текущего пользователя.

Объект _расширяет_ тип [`Cubux.User`][Cubux.User] следующими полями:

Поле | Тип | Описание
---- | --- | --------
`mail` | `string` | E-mail
`name` | `string` | Имя
`family` | `string` | Фамилия
`country_code` | `string(3)` | Код страны
`notify_language` | `string`, NULL | Язык уведомлений
`username` _(только чтение)_ | `string` | Отображаемое имя - конкатенация имени и фамилии
`uuid` _(только чтение)_ | `uuid` | UUID

[Cubux.User]: ../user.md
