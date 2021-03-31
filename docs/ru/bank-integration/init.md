Запрос `init`
=============

Описание действия для подключения. Используется при подключении
(connect) и обновлении данных авторизации (reconnect).

```
GET /api/v2/bank/auth/init/<handler_name>
```

*   `handler_name` - значение поле `handler_name` банка
    [`Cubux.Bank`][Cubux.Bank].

Ответ:

Поле   | Тип | Описание
------ | --- | --------
`type` | `enum("form", "oauth")` | Способ аутентификации
... | | остальные поля, см. далее

### `type: "form"`

Остальные поля:

Поле   | Тип | Описание
------ | --- | --------
`form` | [`Cubux.BankSync.PreferenceForm`][Cubux.BankSync.PreferenceForm] | Описание формы, которую пользователь должен заполнить

В дальнейший запрос [`create`][api-create] и [`reconnect`][api-reconnect] необходимо отправлять данные,
введённые пользователем. Имена полей в теле — это имена полей из
описания формы, а значения - соответствующие значения, введённые
пользователем.

### `type: "oauth"`

Остальные поля:

Поле   | Тип | Описание
------ | --- | --------
`request` | [`Cubux.BankSync.RequestInfo`][Cubux.BankSync.RequestInfo] | Параметры для перехода в новой вкладке или в новом окне

По окончании работы полученные параметры необходимо будет отправить в
дальнейшем запросе [`create`][api-create] или [`reconnect`][api-reconnect].


[api-create]: ./create.md
[api-reconnect]: ./reconnect.md
[Cubux.Bank]: ../type/global/bank.md
[Cubux.BankSync.PreferenceForm]: ../type/bank-sync/preference-form.md
[Cubux.BankSync.RequestInfo]: ../type/bank-sync/request-info.md
