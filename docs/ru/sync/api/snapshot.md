Запрос снапшота
===============

```
GET <context-url>
```

Код | Тело | Описание
--- | ---- | --------
200 | [`Cubux.Sync.Response`][Cubux.Sync.Response] | Данные в поле `data` были готовы заранее
202 | [`Cubux.Sync.Response`][Cubux.Sync.Response] | Обработка поставлена в очередь. В поле `ticket` указан тикет для отслеживания результата.
304 | — | В кеше клиента содержатся актуальные данные, если клиент использует HTTP кеширование.

Прочие коды ответов 4xx и 5xx должны обрабатываться согласно
[спецификации HTTP][http]


#### Пример

Запрос:

    GET /api/v2/sync/user HTTP/1.1
    Host: www.cubux.net
    Authorization: Bearer bd21026244e41a126d69f15ea9d1ac76579f69e3

Ответ, данные уже были готовы ранее:

    HTTP/1.1 200 OK
    Content-Type: application/json; charset=UTF-8
    ...

    {
        "ticket": null,
        "data": {
            "revision":      "a733351e-50c3-4c87-9af6-6a7ab48d49f8",
            "serial":        294,
            "created_at":    "2017-10-19T06:21:47Z",
            "objects": {
                "me": {
                    "uuid": "0fdafba5-b3e6-47d8-bd12-c2b23957598e",
                    "notify_language": null,
                    "username": "Пупкин Василий"
                },
                messages: [],
                teams: [
                    {
                        "role_name": "admin",
                        "team_uuid": "ea30ef9d-dc5c-4a48-9325-a005145307ee",
                        "team": {
                            "uuid": "ea30ef9d-dc5c-4a48-9325-a005145307ee",
                            "title": "Пупкин Василий",
                            "default_currency_code": "RUB",
                            "time_zone": null,
                            "week_start": null
                        }
                    }
                ]
            }
        }
    }

Ответ, обработка поставлена в очередь:

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


[Cubux.Sync.Response]: ../../type/sync/response.md
[http]: https://tools.ietf.org/html/rfc7231
