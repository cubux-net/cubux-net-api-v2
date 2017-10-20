Тип `Cubux.Sync.UserData`
=========================

Словарь объектов для контекста [данных пользователя][context-user].

Используется в:

*   [`Cubux.Sync.Data`][Cubux.Sync.Data]
*   [`Cubux.Sync.DataDiff`][Cubux.Sync.DataDiff]
*   [`Cubux.Sync.DataPatch`][Cubux.Sync.DataPatch]

Объекты в `objects`:

Поле | Тип | Описание
---- | --- | --------
`me`       | [`Cubux.Me`][Cubux.Me] | Данные профайла текущего пользователя
`messages` | `Array:`[`Cubux.UserMessage`][Cubux.UserMessage] | Уведомления
`teams`    | `Array:`[`Cubux.MyTeam`][Cubux.MyTeam] | Команды, в которых пользователь является участником


[context-user]: ../../sync/context/user.md
[Cubux.Me]: ../user/me.md
[Cubux.UserMessage]: ../user/user-message.md
[Cubux.MyTeam]: ../user/team.md
[Cubux.Sync.Data]: data.md
[Cubux.Sync.DataDiff]: data-diff.md
[Cubux.Sync.DataPatch]: data-patch.md
