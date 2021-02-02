Тип `Cubux.Bank`
================

Объект со следующими полями:

Поле           | Тип          | Описание
-------------- | ------------ | --------
**`uuid`** PK  | `uuid`       | UUID
`name`         | `string`     | Название
`country_code` | `string(3)`  | Код страны [`Cubux.Country`][Cubux.Country] из поля `code`
`logo`         | `url`, NULL  | Ссылка на растровый логотип (PNG, JPG, GIF)
`logo_vector`  | `url`, NULL  | Ссылка на векторный логотип (SVG)

Название банка указано на языке страны, в которой он находится, или
на английском.


[Cubux.Country]: country.md
