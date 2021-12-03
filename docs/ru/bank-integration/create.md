Запрос `create`
===============

Создание логина. Используется при подключении (connect).

```
POST /api/v2/bank/auth/<handler_name>
```

*   `handler_name` - значение поле `handler_name` банка
    [`Cubux.Bank`][Cubux.Bank].

В теле запрос указываются параметры, собранные по результатам действия
пользователя после соответствующего запроса [`init`][api-init].

Если поддерживается `fetch_since` (`supportFetchSince` был `true` в
результате [`init`][api-init]), то в теле также может быкать указано
поле `fetch_since` с датой начала (`yyyy-mm-dd`).

Ответ:

Код | Тело | Описание
--- | ---- | --------
200 | [`Cubux.BankSync.AuthLogin`][Cubux.BankSync.AuthLogin] | Логин создан, аутентификация пройдена
201 | [`Cubux.BankSync.AuthLogin`][Cubux.BankSync.AuthLogin] | Логин создан, но необходимо интерактивное подтверждение
422 | `Array:`[`Cubux.ValidationError`][Cubux.ValidationError] | Отправленные данные не соответствуют ожиданиям по вине разработчика клиента.


[api-init]: ./init.md
[Cubux.BankSync.AuthLogin]: ../type/bank-sync/auth-login.md
[Cubux.ValidationError]: ../type/validation-error.md
