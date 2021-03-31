Запрос `interactive-continue`
=============================

Отправка формы интерактивной фазы

```
POST /api/v2/bank/auth/<loginUuid>/interactive
```

*   `loginUuid` - UUID логина
    [`Cubux.BankSync.AuthLogin`][Cubux.BankSync.AuthLogin].

В теле запрос указываются параметры, собранные по форме из запроса
[`interactive-form`][api-interactive-form].

Ответ: идентичен ответу на запрос [`create`][api-create].


[api-create]: ./create.md
[api-interactive-form]: ./interactive-form.md
[Cubux.BankSync.AuthLogin]: ../type/bank-sync/auth-login.md
