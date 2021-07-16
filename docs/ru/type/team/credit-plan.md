Тип `Cubux.CreditPlan`
======================

Пункт графика платежей по кредиту.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`  | UUID
`credit_uuid` | `uuid`  | **Обязательно**. UUID кредита [`Cubux.Credit`][Cubux.Credit]. Не может быть изменён после создания.
`date`        | `date`  | **Обязательно**. Дата
`amount`      | `float` | **Обязательно**. Сумма
`operation_uuid` | `uuid`, NULL | UUID операции [`Cubux.CreditOperation`][Cubux.CreditOperation].

*   Пункт графика считается исполненным, если к нему привязана операция
    [`Cubux.CreditOperation`][Cubux.CreditOperation] в поле
    `operation_uuid`.
*   Сумма, оставшаяся к погашению, равна сумме по всем неисполненным
    пунктам графика.


[Cubux.Credit]: ./credit.md
[Cubux.CreditOperation]: ./credit-operation.md
