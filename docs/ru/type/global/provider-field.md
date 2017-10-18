Тип `Cubux.ProviderField`
=========================

Объект со следующими полями:

Поле             | Тип       | Описание
---------------- | --------- | --------
`name`           | `string`  | Имя, используемое для отправки данных пользователя
`nature`         | `enum("text", "password", "select", "hidden")` | Тип поля
`english_name`   | `string`  | Человекопонятное название на английском языке
`localized_name` | `string`  | Человекопонятное название на языке страны, которой принадлежит провайдер
`position`       | `int`     | Порядковый номер поля в форме
`optional`       | `boolean` | Если `true`, то поле НЕобязательно для заполнения
`options`        | `Array:`[`Cubux.ProviderFieldOption`][Cubux.ProviderFieldOption], NULL | Список вариантов для полей `select`


*Замечание:* Поля `hidden` указаны лишь у провайдеров с режимом `mode` равным
`oauth`.


[Cubux.ProviderFieldOption]: provider-field-option.md
