Тип `Cubux.BudgetPeriod`
========================

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`   | UUID
`entry_uuid`  | `uuid`   | UUID [`Cubux.BudgetEntry`][Cubux.BudgetEntry]. Не может быть изменена после создания.
`start_date`  | `string` | Дата. Для месячного бюджета (`loop="m"`) должен быть год и месяц `yyyy-mm`, а для годового бюджета только год `yyyy`. Не может быть изменена после создания.


[Cubux.BudgetEntry]: ./budget-entry.md
