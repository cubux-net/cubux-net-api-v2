Тип `Cubux.Image`
=================

Изображение. Используется другии объектами для разных нужд.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`                   | UUID
`purpose` | `enum("account", "category", "loan_agent", "draft", "good", "transaction", "target")` | Тип исходного объекта, для которого предназначено изображение
`size_type` | `enum("icon", "photo")`    | Тип размера (см. ниже)
`has_body`  | `boolean`                  | Флаг
`file_size` | `uint64`, NULL             | Размер файла в байтах
`file_type` | `enum("jpg", "png")`, NULL | Тип файла
`width`     | `uint16`, NULL             | Ширина изображения в пикселах
`height`    | `uint16`, NULL             | Высота изображения в пикселах
`created_at`| `datetime`                 | Дата и время создания

**Важно!** Объект изображения может быть создан, но не может быть
изменён.


### Тип размера `size_type`

Для каждого типа объектов в `purpose` используется свой тип размера в `size_type`:

*   `icon`: для типов `"account"`, `"category"`, `"loan_agent"` и `"target"`;
*   `photo`: для типов `"draft"`, `"good"` и `"transaction"`.
