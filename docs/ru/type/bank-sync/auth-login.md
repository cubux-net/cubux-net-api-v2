Тип `Cubux.BankSync.AuthLogin`
==========================

Логин в удалённом банке.

Поле | Тип | Описание
---- | --- | --------
`login_uuid`     | `uuid`    | UUID логина
`is_interactive` | `boolean` | Попал ли в интерактивную фазу
`accounts` | `Array:`[`Cubux.BankSync.AuthAccount`][Cubux.BankSync.AuthAccount] | Счета в удалённом банке


[Cubux.BankSync.AuthAccount]: ./auth-account.md
