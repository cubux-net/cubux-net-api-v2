Тип `Cubux.CryptAccountDisplay`
===============================

Отображение криптовалютного счёта по курсу биржи.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`account_uuid`** PK   | `uuid` | UUID счёта
**`exchanger_uuid`** PK | `uuid` | UUID биржи [`Cubux.CryptExchanger`][Cubux.CryptExchanger]
**`display_currency_code`** PK | `string(16)` | Валюта [`Cubux.Currency`][Cubux.Currency] для отображения баланса. Может быть как криптовалюта, так и фиатная валюта.


[Cubux.CryptExchanger]: ../global/crypt-exchanger.md
[Cubux.Currency]: ../global/currency.md
