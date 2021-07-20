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
`plan_uuid`    | `uuid`, NULL | UUID пункта графика [`Cubux.CreditPlan`][Cubux.CreditPlan].

*   Пункт графика [`Cubux.CreditPlan`][Cubux.CreditPlan] считается
    исполненным, если к нему привязана хотя бы одна операция
    `Cubux.CreditOperation`.
*   Пункт графика [`Cubux.CreditPlan`][Cubux.CreditPlan] может быть
    привязан только к операциям платежей (`type` = `"fee"`). Однако,
    план не обязан быть привязан ко всем платежам (пример: частичное
    досрочное погашение).

[Cubux.Account]: ./account.md
[Cubux.Credit]: ./credit.md
[Cubux.CreditPlan]: ./credit-plan.md
[Cubux.Transaction]: ./transaction.md
