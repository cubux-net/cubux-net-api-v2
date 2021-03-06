Тип `Cubux.LoanHistory`
=======================

Долговая операция.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK       | `uuid`       | UUID
`type` | `enum("credit", "debit")` | **Обязательно**. Направление операции. `"credit"` — движение от Агента к Команде. `"debit"` — от Команды к Агенту.
`agent_uuid`        | `uuid`       | **Обязательно**. UUID долгового агента [`Cubux.LoanAgent`][Cubux.LoanAgent]
`amount`            | `float`      | **Обязательно**. Сумма, которую отдал (или получил) Агент
`currency_code`     | `string(3)`  | **Обязательно**. Валюта для Суммы Агента \*1)
`account_uuid`      | `uuid`, NULL | UUID счета, на который поступили (или с которого списаны) средства
`account_amount`    | `float`      | **Обязательно**. Сумма, поступившая или списанная с указанного Счета \*2)
`account_currency_code` | `string` | **Обязательно**. Валюта суммы, поступившей на Счёт \*2)
`deal_uuid` _(только чтение)_ | `uuid`, NULL | UUID транзакции [`Cubux.Transaction`][Cubux.Transaction]
`description`       | `string`     | Описание
`date`              | `date`       | Дата операции

**\*1)** Различные Валюты Агента `currency_code` для одного и того же
Агента следует учитывать независимо друг от друга. Т.е. можно
одновременно брать в долг, например, в рублях RUB и тому же Агенту
давать в долг, например, в долларах USD.

**\*2)** В операции могут быть разные валюты Агента и Счёта. Например,
заняли у Агента 10 USD (`amount` = `10`, `currency_code` = `"USD"`), а
на Счёт фактически поступило 623.17 RUB (`account_amount` = `623.17`,
`account_currency_code` = `"RUB"`).


[Cubux.LoanAgent]: loan-agent.md
[Cubux.Transaction]: transaction.md
