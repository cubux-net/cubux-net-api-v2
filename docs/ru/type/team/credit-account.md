Тип `Cubux.CreditAccount`
=========================

Связь со счетами для погашения кредита.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK   | `uuid`    | UUID
`credit_uuid`   | `uuid`    | **Обязательно**. UUID кредита [`Cubux.Credit`][Cubux.Credit].
`account_uuid`  | `uuid`    | **Обязательно**. UUID счёта [`Cubux.Account`][Cubux.Account].
`sort`          | `integer` | Порядковый номер для сортировки от `0` до `32767`.


[Cubux.Account]: ./account.md
[Cubux.Credit]: ./credit.md
