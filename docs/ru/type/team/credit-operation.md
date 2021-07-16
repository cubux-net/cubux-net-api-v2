Тип `Cubux.CreditOperation`
===========================

Операция по кредиту.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK  | `uuid`       | UUID
`credit_uuid`  | `uuid`       | **Обязательно**. UUID кредита [`Cubux.Credit`][Cubux.Credit]. Не может быть изменён после создания.
`type` | `enum("credit", "fee")`| **Обязательно**. Тип операции: получение кредита или погашение. Не может быть изменён после создания.
`amount`       | `float`      | **Обязательно**. Сумма.
`date`         | `date`       | **Обязательно**. Дата операции.
`account_uuid` | `uuid`, NULL | UUID счёта [`Cubux.Account`][Cubux.Account]. Обязательно, когда указан `deal_uuid`.
`deal_uuid`    | `uuid`, NULL | UUID транзакции [`Cubux.Transaction`][Cubux.Transaction].


[Cubux.Account]: ./account.md
[Cubux.Credit]: ./credit.md
[Cubux.Transaction]: ./transaction.md
