Тип `Cubux.Provider`
====================

**УСТАРЕВШЕЕ**

Объект со следующими полями:

Поле              | Тип             | Описание
----------------- | --------------- | --------
**`id`** PK       | `uint`          | ID
`automatic_fetch` | `boolean`       | Возможно ли автоматическое обновление данных для Логинов
`code`            | `string`        | Уникальное имя для технических нужд
`fields`          | `Cubux.ProviderFieldset` (см. ниже) | Описание полей
`home_url`        | `url`           | URL домашней страницы банка
`instruction`     | `locale-string` | Текст, поясняющий пользователю, что нужно сделать, чтобы авторизовать приложение
`interactive`     | `boolean`       | Требует ли провайдер интерактивного подтверждения для аутентификации
`mode`            | `enum("api", "web", "oauth")` | Способ аутентификации
`name`            | `string`        | Название на языке страны


### Тип `Cubux.ProviderFieldset`

Объект со следующими полями:

Поле          | Тип | Описание
------------- | --- | --------
`required`    | `Array:`[`Cubux.ProviderField`][Cubux.ProviderField] | Поля для первого этапа создания логина
`interactive` | `Array:`[`Cubux.ProviderField`][Cubux.ProviderField] | Поля, участвующие в интерактивных этапах


[Cubux.ProviderField]: provider-field.md
