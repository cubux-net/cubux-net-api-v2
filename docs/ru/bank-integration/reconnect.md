Запрос `reconnect`
==================

Обновление данных аутентификации.

```
POST /api/v2/bank/auth/<loginUuid>/reconnect
```

*   `loginUuid` - UUID логина
    [`Cubux.BankSync.AuthLogin`][Cubux.BankSync.AuthLogin].

В теле запрос указываются параметры, собранные по результатам действия
пользователя после соответствующего запроса [`init`][api-init].

Ответ: идентичен ответу на запрос [`create`][api-create].


[api-create]: ./create.md
[api-init]: ./init.md
[Cubux.BankSync.AuthLogin]: ../type/bank-sync/auth-login.md
[Cubux.ValidationError]: ../type/validation-error.md
