Экспорт в Excel
===============

```
POST /api/v2/analysis/export/team/{teamUuid}/xls
```

В теле может передаваться объект со следующими свойствами. Любое из
свойств может отсутствовать в объекте.

Поле | Тип | Описание
---- | --- | --------
`source` | `enum("month", "category")` | Способ представления данных: по месяцам или по категориям. По умолчанию по месяцам.
`forcePieChart` | `0`, `1` | Использовать ли круговой график-пирог. По умолчанию `0`.
`types` | `Array: enum("income", "expense", "transfer")` | Типы исходных данных. Когда `source`=`month` (по месяцам) И `forcePieChart`=`0` (круговой график отключён), типы `"income"` и `"expense"` могут использоваться одновременно или отдельно, может быть использован тип `"transfer"` отдельно. В остальных случаях должен быть указан только один тип `"income"` или `"expense"`.
`since` | `month` | Начало периода. По умолчанию январь текущего года на момент запроса.
`until` | `month` | Конец периода. По умолчанию декабрь текущего года на момент запроса.
`categories` | `Array: uuid` | Фильтрация по указанным категориям.
`accounts` | `Array: uuid` | Фильтрация по указанным счетам.
`projects` | `Array: uuid` | Фильтрация по указанным проектам.

Ответ: бинарный, XLSX файл.
