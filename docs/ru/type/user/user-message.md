Тип `Cubux.UserMessage`
=======================

Уведомление пользователю.

Поле | Тип | Описание
---- | --- | --------
**`message_uuid`** PK | `uuid` | UUID
`is_new` | `boolean` | Новое, непрочитанное
`created_at` | `datetime` | Дата и время получения
`translations` | `Array:`[`Cubux.UserMessageTranslation`][Cubux.UserMessageTranslation] | Контент на разных языках

Уведомление можно пометить прочитанным или удалить.


[Cubux.UserMessageTranslation]: ./user-message-translation.md
