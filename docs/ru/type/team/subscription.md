Тип `Cubux.TeamSubscription`
============================

Состояние подписки.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`deadline` (_deprecated_) | `datetime`, NULL |
`features` | `Array: Cubux.TeamSubscription.Feature` | Статусы активности того или иного функционала. В массиве всегда присутствуют статусы по всем существующим функциям.
`gift_reason` | `string`, NULL | Код причины подарка подписки
`is_gift` | `boolean` | Является ли подписка подарком
`since` | `datetime` | Время начала действия подписки
`type` | `enum("premium")`, NULL | Тип подписки. NULL - бесплатная подписка по умолчанию.
`until` | `datetime` | Время окончание действия подписки

### Тип `Cubux.TeamSubscription.Feature`

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`active` | `boolean` | Статус активности функционала
`name` | `enum("app_sync", "bank_sync")` | Имя функционала
