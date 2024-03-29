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
`accounts_access` | `Array:`[`Cubux.AccountAccess`][Cubux.AccountAccess] | Права пользователей на счета
`accounts_groups` | `Array:`[`Cubux.AccountGroup`][Cubux.AccountGroup] | Группы для счетов
`accounts_mentions` | `Array:`[`Cubux.AccountMention`][Cubux.AccountMention] | Упоминания счетов в уведомлениях
`budget_entries` | `Array:`[`Cubux.BudgetEntry`][Cubux.BudgetEntry] | Записи бюджета
`budget_periods` | `Array:`[`Cubux.BudgetPeriod`][Cubux.BudgetPeriod] | Периоды бюджета
`budget_period_categories` | `Array:`[`Cubux.BudgetPeriodCategory`][Cubux.BudgetPeriodCategory] | Суммы бюджета
`categories`     | `Array:`[`Cubux.Category`][Cubux.Category] | Категории
`credits`        | `Array:`[`Cubux.Credit`][Cubux.Credit] | Кредиты
`credits_accounts` | `Array:`[`Cubux.CreditAccount`][Cubux.CreditAccount] | Связи кредитов со счетами для погашения
`credits_operations` | `Array:`[`Cubux.CreditOperation`][Cubux.CreditOperation] | Операции по кредиту
`credits_plans`  | `Array:`[`Cubux.CreditPlan`][Cubux.CreditPlan] | Пункты графиков погашения кредитов
`drafts`         | `Array:`[`Cubux.Draft`][Cubux.Draft] | Чеки
`goods`          | `Array:`[`Cubux.Good`][Cubux.Good] | Справочник товаров для списка покупок
`images`         | `Array:`[`Cubux.Image`][Cubux.Image] | Изображения
`loan_agents`    | `Array:`[`Cubux.LoanAgent`][Cubux.LoanAgent] | Долговые агенты
`loan_history`   | `Array:`[`Cubux.LoanHistory`][Cubux.LoanHistory] | Долговые операции
`loan_status`    | `Array:`[`Cubux.LoanStatus`][Cubux.LoanStatus] | Статус долга
`participants`   | `Array:`[`Cubux.Participant`][Cubux.Participant] | Участники команды
`plans`          | `Array:`[`Cubux.Plan`][Cubux.Plan] | Плановые операции
`plans_confirms` | `Array:`[`Cubux.PlanConfirm`][Cubux.PlanConfirm] | Неподтвержденные плановые операции
`projects`       | `Array:`[`Cubux.Project`][Cubux.Project] | Проекты
`receipt_positions` | `Array:`[`Cubux.ReceiptPosition`][Cubux.ReceiptPosition] | Позиции сканированных чеков
`receipts`       | `Array:`[`Cubux.Receipt`][Cubux.Receipt] | Сканированные чеки
`shop_items`     | `Array:`[`Cubux.ShopItem`][Cubux.ShopItem] | Позиции в списках покупок
`shop_lists`     | `Array:`[`Cubux.ShopList`][Cubux.ShopList] | Списки покупок
`subscription`   | `Array:`[`Cubux.TeamSubscription`][Cubux.TeamSubscription] | Статус подписки команды
`targets`        | `Array:`[`Cubux.Target`][Cubux.Target] | Цели
`targets_reserves` | `Array:`[`Cubux.TargetReserveTransaction`][Cubux.TargetReserveTransaction] | Транзакции резервов целей
`transactions`   | `Array:`[`Cubux.Transaction`][Cubux.Transaction] | Транзакции
`transfer_extras` | `Array:`[`Cubux.TransferExtra`][Cubux.TransferExtra] | Дополнительная информация об импортированных переводах
`users`          | `Array:`[`Cubux.UserBacklog`][Cubux.UserBacklog] | История участников команды

**Важно**: Объекты в перечисленных ниже полях выдаются сервером в
порядке их физического создания на сервере. Клиенту рекомендуется
сохранять такой порядок следования при выводе пользователю. При создании
новых данных локально также рекомендуется запоминать порядок создания, и
отправлять на сервер именно в таком порядке. Всё это поможет
пользователю видеть записи более-менее в одном порядке на всех
устройствах. Поля следующие:

*   `loan_history`
*   `plans`
*   `plans_confirms`
*   `targets_reserves`
*   `transactions`


[context-team]: ../../sync/context/team.md
[Cubux.Account]: ../team/account.md
[Cubux.AccountAccess]: ../team/account-access.md
[Cubux.AccountGroup]: ../team/account-group.md
[Cubux.AccountMention]: ../team/account-mention.md
[Cubux.BudgetEntry]: ../team/budget-entry.md
[Cubux.BudgetPeriod]: ../team/budget-period.md
[Cubux.BudgetPeriodCategory]: ../team/budget-period-category.md
[Cubux.Category]: ../team/category.md
[Cubux.Credit]: ../team/credit.md
[Cubux.CreditAccount]: ../team/credit-account.md
[Cubux.CreditOperation]: ../team/credit-operation.md
[Cubux.CreditPlan]: ../team/credit-plan.md
[Cubux.Draft]: ../team/draft.md
[Cubux.Good]: ../team/good.md
[Cubux.Image]: ../team/image.md
[Cubux.LoanAgent]: ../team/loan-agent.md
[Cubux.LoanHistory]: ../team/loan-history.md
[Cubux.LoanStatus]: ../team/loan-status.md
[Cubux.Participant]: ../team/participant.md
[Cubux.PlanConfirm]: ../team/plan-confirm.md
[Cubux.Plan]: ../team/plan.md
[Cubux.Project]: ../team/project.md
[Cubux.ReceiptPosition]: ../team/receipt-position.md
[Cubux.Receipt]: ../team/receipt.md
[Cubux.ShopItem]: ../team/shop-item.md
[Cubux.ShopList]: ../team/shop-list.md
[Cubux.Sync.DataDiff]: data-diff.md
[Cubux.Sync.DataPatch]: data-patch.md
[Cubux.Sync.Data]: data.md
[Cubux.TargetReserveTransaction]: ../team/target-reserve-transaction.md
[Cubux.Target]: ../team/target.md
[Cubux.TeamInfo]: ../team/info.md
[Cubux.TeamSubscription]: ../team/subscription.md
[Cubux.Transaction]: ../team/transaction.md
[Cubux.TransferExtra]: ../team/transfer-extra.md
[Cubux.UserBacklog]: ../team/user-backlog.md
