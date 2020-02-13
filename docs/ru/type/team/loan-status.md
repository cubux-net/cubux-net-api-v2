Тип `Cubux.LoanStatus`
======================

Общая информация о долге данного агента [`Cubux.LoanAgent`][Cubux.LoanAgent]
по данной валюте.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`agent_uuid`** PK | `uuid` | UUID агента [`Cubux.LoanAgent`][Cubux.LoanAgent]
**`currency_code`** PK | `string(3)` | Код валюты
`comment` | `string` | Комментарий
`deadline` | `date`, NULL | Дата, указывающая срок возврата долга
`notice_before_days` | `uint16`, NULL | Напомнить за указанное количество дней до срока возврата `deadline`
`notice_to` | `string`, NULL | E-mail для напоминания
`notice_to_name` | `string`, NULL | Имя получателя для отправки напоминания `notice_to`


[Cubux.LoanAgent]: loan-agent.md
