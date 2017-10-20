Тип `Cubux.Sync.DataPatch`
==========================

Пакет изменений клиента для отправки на сервер.

Применение: [Отправка изменений][api-submit].

Объект со следующими полями:

Поле              | Тип            | Описание
----------------- | -------------- | --------
`objects`         | `object`, NULL | Словарь обновленных и созданых объектов данного контекста
`deleted_objects` | `object`, NULL | Словарь удалений объектов данного контекста
`serial`          | `uint64`, NULL | Произвольное число для нужд разработчика. Значение будет фигурировать в ответном [тикете][ticket] в поле `client_serial`.

Оба поля `objects` и `deleted_objects` не могут быть NULL отновременно.

Содержимое полей `objects` и `deleted_objects` заполняется согласно
данному контексту аналогично объекту
[`Cubux.Sync.DataDiff`][Cubux.Sync.DataDiff], который приходит в данных
на [запрос разницы][api-diff].

Однако, в отличае от [`Cubux.Sync.DataDiff`][Cubux.Sync.DataDiff],
удаление объектов с простым первичным ключом может передаваться как в
виде простых значений, так и в виде объектов с единственным ключевым
полем (в том числе и оба варианта сразу):

    {
        "deleted_objects": {
            "accounts": [
                "265ae802-5418-4ac0-b777-ed6855787453",
                "aeedcdd5-01fb-4a5c-973f-833c45872ee9",
                {
                    "uuid": "49196ae8-5853-482f-ae13-08dfd9d49577"
                },
                {
                    "uuid": "c4f6f1ea-becd-44fd-89cb-78c8873964c5"
                },
                "aeedcdd5-01fb-4a5c-973f-833c45872ee9"
            ],
            "accounts_access": [
                {
                    "user_uuid":    "0fdafba5-b3e6-47d8-bd12-c2b23957598e",
                    "account_uuid": "265ae802-5418-4ac0-b777-ed6855787453"
                },
                ...
            },
            ...
        }
    }



[api-diff]: ../../sync/api/diff.md
[api-submit]: ../../sync/api/submit.md
[ticket]: ticket.md
[Cubux.Sync.DataDiff]: data-diff.md
