Тип `Cubux.PlanConfirm`
=======================

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK   | `uuid`   | UUID
`account_uuid`  | `uuid`   | **Обязательно**. UUID счета [`Cubux.Account`][Cubux.Account]
`amount`  | `decimal(.10)` | **Обязательно**. Сумма операции в валюте счета
`category_uuid` | `uuid`   | **Обязательно**. UUID категории [`Cubux.Category`][Cubux.Category]
`date`          | `date`   | Дата операции. По умолчанию - текущая дата.
`description`   | `string` | Описание
`project_uuid` | `uuid`, NULL | UUID проекта [`Cubux.Project`][Cubux.Project]
`type` | `enum("expense", "income")` | **Обязательно**. Тип операции.

### `date`

Операции с датой ранее 3 полных лет удаляются 1 раз в сутки.

В веб версии можно встретить предупреждение о том, что дата не должна
быть ранее, чем 1 января 2 года назад. Например, если сейчас 2022 год,
то предупреждение будет выведено для дат ранее 01.01.2020.

Для АПИ синхронизации жесткого запрета нет, как для обратной
совместимости, так и для удобства пользователя.


[Cubux.Account]: account.md
[Cubux.Category]: category.md
[Cubux.Project]: project.md
