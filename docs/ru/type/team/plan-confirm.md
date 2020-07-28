Тип `Cubux.PlanConfirm`
=======================

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK   | `uuid`   | UUID
`account_uuid`  | `uuid`   | **Обязательно**. UUID счета [`Cubux.Account`][Cubux.Account]
`amount`        | `float`  | **Обязательно**. Сумма операции в валюте счета
`category_uuid` | `uuid`   | **Обязательно**. UUID категории [`Cubux.Category`][Cubux.Category]
`date`          | `date`   | Дата операции. По умолчанию - текущая дата.
`description`   | `string` | Описание
`type` | `enum("expense", "income")` | **Обязательно**. Тип операции.


[Cubux.Account]: account.md
[Cubux.Category]: category.md
