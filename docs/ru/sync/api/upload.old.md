Загрузка файла (устаревший способ)
==================================

> **Важно!** Этот способ является устаревшим и оставлен для обратной
> совместимости. Используйте актуальную [загрузку изображений][upload-image].

Подробнее о механике загрузки файлов см. [Загрузка файлов][uploads].

В ответе на запрос [подготовки загрузки][uploader] содержится объект
[`Cubux.Upload.Params`][Cubux.Upload.Params], содержащий URI адрес
для выполнения данного запроса:

```
PUT <uri> HTTP/1.1
Content-Type: application/octet-stream
Content-Length: ...
```

В теле запроса передается тело файла в бинарном виде (т.е. в сыром виде
без какого-либо перекодирования).

Код | Тело | Описание
--- | ---- | --------
200 | [`Cubux.Upload.BlobReference`][Cubux.Upload.BlobReference] | Объект содержит код, который можно использовать в данных основного API для ссылки на этот файл
401 | — | Срок жизни данных аутентификации устарел (данные содержатся в URI) либо они неверны. Необходимо повторить запрос [подготовки загрузки][uploader].
422 | `Array:`[`Cubux.ValidationError`][Cubux.ValidationError] | Отправленый файл не соответствуют требованиям. Ошибки можно показать пользователю согласно ТЗ клиента.

Прочие коды ответов 4xx и 5xx должны обрабатываться согласно
[спецификации HTTP][http]

**Важно**: Не забывайте указывать заголовок `Content-Length` в запросе.
Если этого не делать, то технически концом файла может служить лишь
разрыв соединения клиентом, как в HTTP/1.0. Если в этом случае не
закрыть соединение после конца файла, то сервер отклонит запрос, указав
статус 4xx.

**Важно**: Передавать заголовок `Authorization` не следует, т.к.
параметры запроса в URI уже содержат необходимую информацию для
авторизации. Отправка заголовка `Authorization` будет мешать.

**Важно**: Данные для авторизации, которые содержатся в URI, имеют
ограниченый срок жизни. См. [Ограничения][limitations].


#### Пример

Предроложим, запрос подготовки загрузки вернул следующий ответ:

    {
        "uri":     "https://file.cubux.net/api/upload?...",
        "expires": "2017-10-19T06:21:47Z"
    }

Тогда запрос загрузки файла будет выглядеть так:

    PUT /api/upload?... HTTP/1.1
    Host: file.cubux.net
    Content-Type: application/octet-stream
    Content-Length: ...

    бинарное тело файла...

Ответ:

    HTTP/1.1 200 OK
    Content-Type: application/json: charset=UTF-8

    {
        "blobKey": "Bbrno6_wrYTQlHuVBe23ULDauANXpWge"
    }


[http]: https://tools.ietf.org/html/rfc7231
[limitations]: ../20-limitations.md
[upload-image]: ./upload-image.md
[uploader]: ./uploader.old.md
[uploads]: ../10-uploads.old.md
[Cubux.Upload.BlobReference]: ../../type/upload/blob-reference.md
[Cubux.Upload.Params]: ../../type/upload/params.md
[Cubux.ValidationError]: ../../type/validation-error.md
