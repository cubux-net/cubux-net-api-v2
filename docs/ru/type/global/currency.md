Тип `Cubux.Currency`
====================

Объект со следующими полями:

Поле          | Тип               | Описание
------------- | ----------------- | --------------------------------------------
**`code`** PK | `string(3)`       | Код из трех буков по [ISO][iso-currency-code]
`prefix`      | `string(3)`, NULL | Префикс для форматирования суммы
`postfix`     | `string(3)`, NULL | Суффикс для форматирования суммы
`symbol`      | `string(3)`, NULL | Символ валюты
`title`       | `locale-string`   | Название валюты


[iso-currency-code]: https://en.wikipedia.org/wiki/ISO_4217 "ISO 4217 alpha-3"
