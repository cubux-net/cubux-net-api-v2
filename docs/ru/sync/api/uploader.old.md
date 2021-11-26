Подготовка загрузки файлов (устаревший способ)
==============================================

> **Важно!** Этот способ является устаревшим и оставлен для обратной
> совместимости. Используйте актуальную [загрузку изображений][upload-image].

Подробнее о механике загрузки файлов см. [Загрузка файлов][uploads].

В настоящее время загрузка файлов доступна только в контексте команды.

```
POST <context-url>/uploader
```

В теле запроса отправляется объект
[`Cubux.Upload.Init`][Cubux.Upload.Init].

Код | Тело | Описание
--- | ---- | --------
200 | [`Cubux.Upload.Params`][Cubux.Upload.Params] | Параметры для выполнения запросов [загрузки файлов][api-upload]
422 | `Array:`[`Cubux.ValidationError`][Cubux.ValidationError] | Отправленные данные не соответствуют ожиданиям по вине разработчика клиента.

Прочие коды ответов 4xx и 5xx должны обрабатываться согласно
[спецификации HTTP][http]


#### Пример

Подготовка загрузки чеков в конкретную команду:

    POST /api/v3/sync/team/ea30ef9d-dc5c-4a48-9325-a005145307ee/uploader HTTP/1.1
    Host: app.cubux.net
    Authorization: Bearer bd21026244e41a126d69f15ea9d1ac76579f69e3
    Content-Type: application/json; charset=UTF-8

    {
        "node_type": "draft"
    }

Ответ

    HTTP/1.1 200 OK
    Content-Type: application/json: charset=UTF-8

    {
        "uri":     "https://file.cubux.net/api/upload?...",
        "expires": "2017-10-19T06:21:47Z"
    }


[api-upload]: upload.old.md
[http]: https://tools.ietf.org/html/rfc7231
[upload-image]: ./upload-image.md
[uploads]: ../10-uploads.old.md
[Cubux.Upload.Init]: ../../type/upload/init.md
[Cubux.Upload.Params]: ../../type/upload/params.md
[Cubux.ValidationError]: ../../type/validation-error.md
