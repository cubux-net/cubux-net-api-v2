Тип `Cubux.Sync.Data`
=====================

Базовый тип, характеризующий снапшот данных в конкретном контексте.

Возникает посредством [запроса снапшота][api-snapshot].

Объект со следующими полями:

Поле         | Тип        | Описание
------------ | ---------- | --------
`revision`   | `uuid`     | UUID ревизии последних изменений
`serial`     | `uint64`   | Порядковый номер последних изменений
`created_at` | `datetime` | Дата регистрации последних изменений
`objects`    | [`Cubux.Sync.GlobalData`][Cubux.Sync.GlobalData], [`Cubux.Sync.TeamData`][Cubux.Sync.TeamData], [`Cubux.Sync.UserData`][Cubux.Sync.UserData] | Словарь объектов данного контекста

UUID ревизии используется для отслеживания изменений.
[Запрос разницы][api-diff] осуществляется с использованием UUID базовой
ревизии, по отношению к которой необходимо получить изменения.

Порядковы номер `serial` всегда гарантировано возрастает в более новых
ревизиях. Для порядкового номера допустимы операции арифметического
сравнения "больше", "меньше" и "равно". Другие арифметические операции
(например, вычитание для попытки узнать "поколение") не имеют смысла.

Дата возникновения ревизии `created_at` необходима для отслеживания
устаревших ревизий. [Запрос разницы][api-diff] ограничен по времени
возникновения базовой ревизии. См. [Ограничения][limitations].

Поле `objects` содержит поля, имена которых соответствуют типам объектов
в данном контексте. Конкретный список полей (разновидности объектов)
см. в описании производных типов для конкретного [контекста][context].

Конкретные экземпляры объектов внутри `objects` несут объекты целиком,
чтобы клиент мог построить свою локальную базу данных "с нуля".


[api-diff]: ../../sync/api/diff.md
[api-snapshot]: ../../sync/api/snapshot.md
[context]: ../../sync/02-context.md
[limitations]: ../../sync/20-limitations.md
[Cubux.Sync.GlobalData]: ./data-global.md
[Cubux.Sync.TeamData]: ./data-team.md
[Cubux.Sync.UserData]: ./data-user.md
