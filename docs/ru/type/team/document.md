Тип `Cubux.Document`
====================

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK  | `uuid`       | UUID
`type`         | `string`     | **Обязательно**. Тип документа (см. ниже)
`category_uuid` | `uuid`      | UUID категории [`Cubux.Category`][Cubux.Category]. Обязательно или нет — зависит от типа `type` (см. ниже).
`date`         | `date`       | Дата
`deal_uuid`    | `uuid`, NULL | UUID транзакции [`Cubux.Transaction`][Cubux.Transaction]
`description`  | `string`     | Описание
`project_uuid` | `uuid`, NULL | UUID проекта [`Cubux.Project`][Cubux.Project]

**Важно**: Поле `type` не может быть изменено после создания.
Используйте вместо этого удаление старого документа и создание нового.

В будущем планируется постепенно избавиться от транзакций
[`Cubux.Transaction`][Cubux.Transaction] в пользу документов.
Связь с транзакцией [`Cubux.Transaction`][Cubux.Transaction] в поле
`deal_uuid` по-настоящему будет нужна в переходный период, когда одни и
те же данные могут передаваться как через старые версии клиентов,
которые ничего не знают о документах, так и через новые. Подробности
перехода пока неизвестны.

## Типы документов

Ниже перечислены поддерживаемые типы документов.

В столбце "Категория" указано, какая категория должна использоваться в
документе соответствующего типа. В случае служебной категории её можно
не указывать — сервер сам подставит нужную категорию. Для остальных
случаев поле `category_uuid` обязательно для заполнения.

В столбце "Транзакция" указаны требования к привязанной транзакции для
обратной совместимости. TBW

Значение `type` | Категория | Транзакция | Описание
--------------- | --------- | ---------- | --------
`cryptBuy` | Служебная: `system_code` = `"transfer"` | ? | Покупка криптовалюты за валюту с обычного счёта
`cryptExpense` | Обычная расходная | — | Расход криптовалюты (оплата товаров/услуг криптовалютой)
`cryptIncome` | Обычная доходная | — | Доход в криптовалюте (за товары/услуги)
`cryptInitialExpense` | Служебная: `system_code` = `"initial_output"` | — | Негативный начальный остаток по криптовалютному счёту
`cryptInitialIncome` | Служебная: `system_code` = `"initial_input"` | — | Положительный начальный остаток по криптовалютному счёту
`cryptSell` | Служебная: `system_code` = `"transfer"` | ? | Продажа криптовалюты за валюту с обычного счёта
`cryptTransfer` | Служебная: `system_code` = `"transfer"` | — | Перевод между криптовалютными счетами

Ниже приведено описание операций для всех типов документов.

### `cryptBuy`

Покупка криптовалюты за обычную валюту.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CryptAccountOperation`][Cubux.CryptAccountOperation] | `0` - in | 1 | Доход по криптовалютному счёту
[`Cubux.AccountOperation`][Cubux.AccountOperation] | `1` - out | 1 | Расход по обычному счёту

### `cryptExpense`

Расход криптовалюты, оплата товаров/услуг криптовалютой.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CryptAccountOperation`][Cubux.CryptAccountOperation] | `1` - out | 1 | Расход по криптовалютному счёту

### `cryptIncome`

Доход в криптовалюте (за товары/услуги).

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CryptAccountOperation`][Cubux.CryptAccountOperation] | `0` - in | 1 | Доход по криптовалютному счёту

### `cryptInitialExpense`

Негативный начальный остаток по криптовалютному счёту.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CryptAccountOperation`][Cubux.CryptAccountOperation] | `1` - out | 1 | Расход по криптовалютному счёту

### `cryptInitialIncome`

Положительный начальный остаток по криптовалютному счёту.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CryptAccountOperation`][Cubux.CryptAccountOperation] | `0` - in | 1 | Доход по криптовалютному счёту

### `cryptSell`

Продажа криптовалюты за валюту с обычного счёта.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.AccountOperation`][Cubux.AccountOperation] | `0` - in | 1 | Доход по обычному счёту
[`Cubux.CryptAccountOperation`][Cubux.CryptAccountOperation] | `1` - out | 1 | Расход по криптовалютному счёту

### `cryptTransfer`

Перевод между криптовалютными счетами.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CryptAccountOperation`][Cubux.CryptAccountOperation] | `0` - in | 1 | Доход по криптовалютному счёту
[`Cubux.CryptAccountOperation`][Cubux.CryptAccountOperation] | `1` - out | 1 | Расход по криптовалютному счёту


[Cubux.AccountOperation]: ./account-operation.md
[Cubux.Category]: ./category.md
[Cubux.CryptAccountOperation]: ./crypt-account-operation.md
[Cubux.Project]: ./project.md
[Cubux.Transaction]: ./transaction.md
