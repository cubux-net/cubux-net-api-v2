Тип `Cubux.PushParsePule`
=========================

Объект со следующими полями:

| Поле        | Тип      | Описание
| ----------- | -------- | --------
| **`id`** PK | `int`    | ID
| `app_id`    | `string` | Идентификатор приложения, для которого применять правило.
| `operation` | `enum("expense", "income")` | Тип итоговой операции.
| `sort`      | `int`    | Порядок сортировки. От `0` до `32767`.
| `country`   | `string` | Необязательно. Страна.
| `patterns`  | `Array:`[`Cubux.PushParsePulePattern`][Cubux.PushParsePulePattern] | Список шаблонов для поиска
| `extra`     |          | Дополнительные произвольные данные


[Cubux.PushParsePulePattern]: ./push-parse-rule-pattern.md
