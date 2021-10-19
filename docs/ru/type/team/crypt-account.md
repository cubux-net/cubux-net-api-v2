Тип `Cubux.CryptAccount`
========================

Криптовалютный счёт.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK    | `uuid`       | UUID
`name`           | `string`     | **Обязательно**. Название
`crypt_currency_code` | `string` | **Обязательно**. Криптовалюта [`Cubux.CryptCurrency`][Cubux.CryptCurrency]
`display_currency_code` | `string`, NULL | Валюта для отображения баланса. Может быть как код криптовалюты [`Cubux.CryptCurrency`][Cubux.CryptCurrency], так и обычной валюты [`Cubux.Currency`][Cubux.Currency].
`exchanger_uuid` | `uuid`, NULL | UUID биржи [`Cubux.CryptExchanger`][Cubux.CryptExchanger] для отображения баланса по курсу
`sort`           | `int`        | Порядковый номер для сортировки от 0 до 32767. Рекомендуется использовать шаг больше 1 для более удобной вставки между соседями. Например: 10, 20, 30, ... или 100, 200, 300, ... Перенумерация соседей при изменении не обязательна, но уместна.
`icon_name`      | `string`     | Имя иконки. Максимум 32 символа.
`icon_uuid`      | `uuid`, NULL | UUID иконки [`Cubux.Image`][Cubux.Image]
`is_hidden`      | `boolean`    | Скрытый
`is_excluded`    | `boolean`    | Не учитывается в общем балансе команды
`is_locked` _(только чтение)_ | `boolean` | Счет блокирован (см. ниже)


### Блокированный счёт

Блокированный счёт не может быть использован для проведения операций.
Например, для счёта настроена интеграция с банком, откуда импортируются
реальные операции.


[Cubux.CryptCurrency]: ../global/crypt-currency.md
[Cubux.CryptExchanger]: ../global/crypt-exchanger.md
[Cubux.Currency]: ../global/crypt-currency.md
[Cubux.Image]: ./image.md
