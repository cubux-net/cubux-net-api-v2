Тип `Cubux.Sync.Response`
=========================

Ответ на запросы основного АПИ.

Объект со следующими полями:

Поле     | Тип | Описание
-------- | --- | --------
`ticket` | [`Cubux.Sync.Ticket`][Cubux.Sync.Ticket], NULL | Тикет
`data`   | [`Cubux.Sync.Data`][Cubux.Sync.Data], [`Cubux.Sync.DataDiff`][Cubux.Sync.DataDiff], NULL | Данные

Ниже приведён список вариантов ответов на различные запросы:

Запрос | Код ответа | `ticket` | `data`
------ | ---------- | -------- | ------
[Снапшот][api-snapshot] | 200 | NULL | [`Cubux.Sync.Data`][Cubux.Sync.Data]
[Снапшот][api-snapshot] | 202 | [`Cubux.Sync.Ticket`][Cubux.Sync.Ticket] | NULL
[Разница][api-diff]     | 200 | NULL | [`Cubux.Sync.DataDiff`][Cubux.Sync.DataDiff]
[Разница][api-diff]     | 202 | [`Cubux.Sync.Ticket`][Cubux.Sync.Ticket] | NULL
[Разница][api-diff]     | 204 | — | —
[Отправка][api-submit]  | 202 | [`Cubux.Sync.Ticket`][Cubux.Sync.Ticket] | NULL

Ниже отдельно приведены варианты успешных ответов `200` на
[запрос по тикету][api-ticket]. Здесь поле `ticket` всегда заполнено
объектом тикета, поэтому вместо него здесь указано поле `status` этого
тикета. Столбец "Начальный запрос" соответствует типу запроса,
породившего данный тикет.

Начальный запрос  | `ticket`.`status` | `data`
----------------- | ----------------- | ------
любой             | кроме `"done"` | NULL
[Снапшот][api-snapshot] | `"done"` | [`Cubux.Sync.Data`][Cubux.Sync.Data]
[Разница][api-diff]     | `"done"` | [`Cubux.Sync.DataDiff`][Cubux.Sync.DataDiff]
[Отправка][api-submit]  | `"done"` | NULL


[api-diff]: ../../sync/api/diff.md
[api-snapshot]: ../../sync/api/snapshot.md
[api-submit]: ../../sync/api/submit.md
[api-ticket]: ../../sync/api/ticket.md
[Cubux.Sync.Data]: data.md
[Cubux.Sync.DataDiff]: data-diff.md
[Cubux.Sync.Ticket]: ticket.md
