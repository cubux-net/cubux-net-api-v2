Тип `Cubux.BankSync.AuthAccount`
================================

Счёт в удаленном банке.

Поле | Тип | Описание
---- | --- | --------
`auth_uuid` | `uuid` | UUID для ссылки из [`Cubux.Account`][Cubux.Account] в поле `auth_uuid`
`currency_code` | `string(3)` | Валюта счёта
`title`         | `string` | Название счёта, если доступно
`last_balance`  | `decimal(.10)`, NULL | Остаток на счету, если доступен


[Cubux.Account]: ../team/account.md
