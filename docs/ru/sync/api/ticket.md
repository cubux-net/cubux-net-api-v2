Запрос тикета
=============

```
GET <context-url>/ticket/<ticket-uuid>
```

Код | Тело | Описание
--- | ---- | --------
200 | [`Cubux.Sync.Response`][Cubux.Sync.Response] | Тикет (возможно, обновлённый) в поле `ticket`. Если запрос данных завершен успешно, то данные в поле `data`.
410 | — | Тикет устарел.

Прочие коды ответов 4xx и 5xx должны обрабатываться согласно
[спецификации HTTP][http]


#### Пример

Запрос:

    GET /api/v2/sync/user/ticket/bc7a1c11-e972-4268-bb85-b348b1745d5a HTTP/1.1
    Host: www.cubux.net
    Authorization: Bearer bd21026244e41a126d69f15ea9d1ac76579f69e3

Ответ, сбор данных завершен:

    HTTP/1.1 200 OK
    Content-Type: application/json; charset=UTF-8
    ...

    {
        "ticket": {
            "uuid":       "bc7a1c11-e972-4268-bb85-b348b1745d5a",
            "client_serial":     null,
            "status":            "done",
            "created_at":        "2017-10-19T05:30:58Z",
            "status_changed_at": "2017-10-19T05:30:58Z",
            "errors":            []
        },
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

Ответ, обработка отклонена:

    HTTP/1.1 200 OK
    Content-Type: application/json; charset=UTF-8
    ...

    {
        "ticket": {
            "uuid":       "bc7a1c11-e972-4268-bb85-b348b1745d5a",
            "client_serial":     null,
            "status":            "aborted",
            "created_at":        "2017-10-19T05:30:58Z",
            "status_changed_at": "2017-10-19T05:30:58Z",
            "errors": [
                {
                    "section": "objects",
                    "entity":  "drafts",
                    "key": {
                        "uuid": "3302773c-3bcf-4b7e-ba02-f97b470e2801"
                    },
                    "attribute": "image_blob",
                    "messages": [
                        {
                            "level":   "user_error",
                            "code":    "input",
                            "message": "File reference is outdated"
                        }
                    ]
                }
            ]
        },
        "data": null
    }


[Cubux.Sync.Response]: ../../type/sync/response.md
[http]: https://tools.ietf.org/html/rfc7231
