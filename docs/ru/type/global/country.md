Тип `Cubux.Country`
===================

Объект со следующими полями:

Поле                    | Тип               | Описание
----------------------- | ----------------- | --------
**`code`** PK           | `string(3)`       | Код из трех буков по [ISO 3166-1 alpha-3][iso-country-3]
`code2`                 | `string(2)`       | Код из двух буков по [ISO 3166-1 alpha-2][iso-country-2]
`default_currency_code` | `string(16)`, NULL | Код основной валюты (см. [`Cubux.Currency`][Cubux.Currency])
`flag`                  | `url`, NULL       | Ссылка на растровый флаг (PNG, JPG, GIF)
`flag_vector`           | `url`, NULL       | Ссылка на векторный флаг (SVG)
`title`                 | `locale-string`   | Название


[iso-country-3]: https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3 "ISO 3166-1 alpha-3"
[iso-country-2]: https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2 "ISO 3166-1 alpha-2"
[Cubux.Currency]: currency.md
