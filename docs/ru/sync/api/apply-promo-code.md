Применение промо кода
=====================

```
PATCH /api/v2/subscription/apply-promo-code/{teamUuid}
```

В теле должен передаваться объект со следующими свойствами.

Поле | Тип | Описание
---- | --- | --------
`code` | `string` | Промо код

Ответ:

Код | Тело | Описание
--- | ---- | --------
200 | [`Cubux.TeamSubscription`][Cubux.TeamSubscription] | 
422 | `Array:`[`Cubux.ValidationError`][Cubux.ValidationError] | Ошибки валидации


[Cubux.TeamSubscription]: ../../type/team/subscription.md
[Cubux.ValidationError]: ../../type/validation-error.md
