Запрос `interactive-form`
=========================

Запрос формы интерактивной фазы.

```
GET /api/v2/bank/auth/<loginUuid>/interactive
```

*   `loginUuid` — UUID логина
    [`Cubux.BankSync.AuthLogin`][Cubux.BankSync.AuthLogin].

Ответ:

Код | Тело | Описание
--- | ---- | --------
200 | [`Cubux.BankSync.PreferenceForm`][Cubux.BankSync.PreferenceForm] | Описание формы
409 | — | Логин не пребывает в интерактивной фазе


[Cubux.BankSync.AuthLogin]: ../type/bank-sync/auth-login.md
[Cubux.BankSync.PreferenceForm]: ../type/bank-sync/preference-form.md
