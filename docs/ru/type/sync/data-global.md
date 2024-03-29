Тип `Cubux.Sync.GlobalData`
===========================

Словарь объектов для контекста [глобальных данных][context-global].

Используется в:

*   [`Cubux.Sync.Data`][Cubux.Sync.Data]
*   [`Cubux.Sync.DataDiff`][Cubux.Sync.DataDiff]

Объекты в `objects`:

Поле | Тип | Описание
---- | --- | --------
`banks`          | `Array:`[`Cubux.Bank`][Cubux.Bank] | Банки
`countries`      | `Array:`[`Cubux.Country`][Cubux.Country] | Страны
`currencies`     | `Array:`[`Cubux.Currency`][Cubux.Currency] | Валюты
`currency_rates` | `Array:`[`Cubux.CurrencyRate`][Cubux.CurrencyRate] | Последние курсы валют
`goods_suggestions` | `Array: string` | Подсказки для товаров в списках покупок. После изменений в запросе разницы будет приходить полный список, как единый неделимый объект


[context-global]: ../../sync/context/global.md
[Cubux.Bank]: ../global/bank.md
[Cubux.Country]: ../global/country.md
[Cubux.Currency]: ../global/currency.md
[Cubux.CurrencyRate]: ../global/currency-rate.md
[Cubux.Sync.Data]: data.md
[Cubux.Sync.DataDiff]: data-diff.md
