Тип `Cubux.Sync.TeamData`
=========================

Словарь объектов для контекста [данных команды][context-team].

Используется в:

*   [`Cubux.Sync.Data`][Cubux.Sync.Data]
*   [`Cubux.Sync.DataDiff`][Cubux.Sync.DataDiff]
*   [`Cubux.Sync.DataPatch`][Cubux.Sync.DataPatch]

Объекты в `objects`:

Поле | Тип | Описание
---- | --- | --------
`info`           | [`Cubux.TeamInfo`][Cubux.TeamInfo] | Информация о команде
`accounts`       | `Array:`[`Cubux.Account`][Cubux.Account] | Счета
`accounts_access` | `Array:`[`Cubux.AccountAccess`][Cubux.AccountAccess] | Правапользователей на счета
`budgets`        | `Array:`[`Cubux.Budget`][Cubux.Budget] | Бюджет
`categories`     | `Array:`[`Cubux.Category`][Cubux.Category] | Категории
`drafts`         | `Array:`[`Cubux.Draft`][Cubux.Draft] | Чеки
`loan_agents`    | `Array:`[`Cubux.LoanAgent`][Cubux.LoanAgent] | Долговые агенты
`loan_history`   | `Array:`[`Cubux.LoanHistory`][Cubux.LoanHistory] | Долговые операции
`participants`   | `Array:`[`Cubux.Participant`][Cubux.Participant] | Участники команды
`plans`          | `Array:`[`Cubux.Plan`][Cubux.Plan] | Плановые операции
`plans_confirms` | `Array:`[`Cubux.PlanConfirm`][Cubux.PlanConfirm] | Неподтвержденные плановые операции
`projects`       | `Array:`[`Cubux.Project`][Cubux.Project] | Проекты
`targets`        | `Array:`[`Cubux.Target`][Cubux.Target] | Цели
`targets_reserves` | `Array:`[`Cubux.TargetReserveTransaction`][Cubux.TargetReserveTransaction] | Транзакции резервов целей
`transactions`   | `Array:`[`Cubux.Transaction`][Cubux.Transaction] | Транзакции


[context-team]: ../../sync/context/team.md
[Cubux.Account]: ../team/account.md
[Cubux.AccountAccess]: ../team/account-access.md
[Cubux.Budget]: ../team/budget.md
[Cubux.Category]: ../team/category.md
[Cubux.Draft]: ../team/draft.md
[Cubux.LoanAgent]: ../team/loan-agent.md
[Cubux.LoanHistory]: ../team/loan-history.md
[Cubux.Participant]: ../team/participant.md
[Cubux.Plan]: ../team/plan.md
[Cubux.PlanConfirm]: ../team/plan-confirm.md
[Cubux.Project]: ../team/project.md
[Cubux.Target]: ../team/target.md
[Cubux.TargetReserveTransaction]: ../team/target-reserve-transaction.md
[Cubux.Transaction]: ../team/transaction.md
[Cubux.TeamInfo]: ../team/info.md
[Cubux.Sync.Data]: data.md
[Cubux.Sync.DataDiff]: data-diff.md
[Cubux.Sync.DataPatch]: data-patch.md
