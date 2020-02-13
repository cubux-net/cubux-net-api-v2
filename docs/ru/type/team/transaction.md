Тип `Cubux.Transaction`
=======================

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`       | UUID
`type` | `enum("plus", "minus", "transfer", "initial", "initial_loan")` | **Обязательно**. Тип транзакции
`account_uuid` | `uuid` | **Обязательно**. UUID счёта. Используется всеми типами транзакций
`currency_code` | `string(3)` | Валюта операции
`amount` | `float` | **Обязательно**. Сумма операции в валюте `currency_code`
`amount_native` _(только чтение)_ | `float` | Сумма в Основной Валюте команды \*1)
`category_uuid` | `uuid` | **Обязательно**. UUID категории
`amount2` | `float`, NULL | Сумма зачисления для транзакций переводов (`type` = `transfer`).
`amount2_native` _(только чтение)_ | `float`, NULL | Сумма зачисления `amount` в Основной Валюте команды \*1)
`currency_code2` | `string(3)` | Валюта суммы зачисления `amount2` для переводов
`account2_uuid` | `uuid`, NULL | UUID счёта зачисления для переводов
`date` | `date` | Дата проведения
`project_uuid` | `uuid`, NULL | UUID проекта [`Cubux.Project`][Cubux.Project]
`description` | `string` | Описание
`link_type` | `enum("loan_history", "receipt", "target_reserve")`, NULL | Тип связанного объекта \*4)
`link_uuid` | `uuid`, NULL | UUID связанного объекта \*4)
`user_uuid` _(только чтение)_ | `uuid`, NULL | Пользователь, совершивший операцию
`imported_data_uuid` | `uuid`, NULL | UUID связи с импортированной транзакцией \*3)
`canUpdate` _(только чтение)_ | `boolean` | Наличие привилегий на изменение
`canDelete` _(только чтение)_ | `boolean` | Наличие привилегий на удаление
`is_imported` _(только чтение)_ | `boolean` | Является ли транзакция импортированной \*2)
`can_join` _(только чтение)_  | `boolean` | Наличие прав на объединение в перевод \*3)
`can_split` _(только чтение)_ | `boolean` | Наличие прав на объединение в перевод \*3)

**\*1)** Остовная Валюта команды указана в данных о команде
[`Cubux.TeamInfo`][Cubux.TeamInfo] в поле `default_currency_code`.

**\*2)** У импортированных транзакций возможно лишь редактирование
категории.

**\*3)** Существует возможность объединить две транзакции прихода
и расхода в одну транзакцию перевода и разделить транзакцию перевода
на приход и расход. \[TBW]
См. также [`Cubux.TransferExtra`][Cubux.TransferExtra].

**\*4)** \[TBW]


#### Типы транзакций `type`

Значение | Описание
-------- | --------
`plus` | Приход
`minus` | Расход
`transfer` | Перевод
`initial` | Начальный остаток _(только чтение)_
`initial_loan` | Начальный долг _(только чтение)_

Транзакции начальных остатков (`type` = `initial`) и долгов (`type` =
`initial_loan`) на сервере создаются, редактируются и удаляются
автоматически при изменении полей `initial_amount` и `initial_date`
у соответствующего счёта [`Cubux.Account`][Cubux.Account]. Эти
транзакции не могут быть созданы, изменены или удалены напрямую с
помощью API.


[Cubux.Account]: account.md
[Cubux.Project]: project.md
[Cubux.TeamInfo]: info.md
[Cubux.TransferExtra]: transfer-extra.md
