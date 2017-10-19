Отправка изменений
==================

```
POST <context-url>
```

В теле запроса отправляется объект
[`Cubux.Sync.DataPatch`][Cubux.Sync.DataPatch].

Код | Тело | Описание
--- | ---- | --------
202 | [`Cubux.Sync.Response`][Cubux.Sync.Response] | Обработка поставлена в очередь. В поле `ticket` указан тикет для отслеживания результата.
422 | `Array:`[`Cubux.ValidationError`][Cubux.ValidationError] | Отправленые данные не соответствуют ожиданиям по вине разработчика клиента.

Прочие коды ответов 4xx и 5xx должны обрабатываться согласно
[спецификации HTTP][http]


#### Пример

Запрос:

    POST /api/v2/sync/user HTTP/1.1
    Host: www.cubux.net
    Authorization: Bearer bd21026244e41a126d69f15ea9d1ac76579f69e3

    {
        "objects": {
            "me": {
                "name":   "Иван"
                "family": "Иванов"
            }
        }
    }

Ответ:

    HTTP/1.1 202 Accepted
    Content-Type: application/json; charset=UTF-8
    ...

    {
        "ticket": {
            "uuid":       "bc7a1c11-e972-4268-bb85-b348b1745d5a",
            "client_serial":     null,
            "status":            "new",
            "created_at":        "2017-10-19T05:30:58Z",
            "status_changed_at": "2017-10-19T05:30:58Z",
            "errors":            []
        },
        "data": null
    }


[Cubux.Sync.DataPatch]: ../../type/sync/data-patch.md
[Cubux.Sync.Response]: ../../type/sync/response.md
[Cubux.ValidationError]: ../../type/validation-error.md
[http]: https://tools.ietf.org/html/rfc7231
