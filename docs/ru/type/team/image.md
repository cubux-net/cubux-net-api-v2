Тип `Cubux.Image`
=================

Изображение. Используется другии объектами для разных нужд.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`                   | UUID
`purpose` | `enum("account", "category", "loan_agent", "draft", "target")` | Тип исходного объекта, для которого предназначено изображение
`size_type` | `enum("icon", "photo")`    | Тип размера (см. ниже)
`has_body`  | `boolean`                  | Флаг
`file_size` | `uint64`, NULL             | 
`file_type` | `enum("jpg", "png")`, NULL | 
`width`     | `uint16`, NULL             | 
`height`    | `uint16`, NULL             | 
`created_at`| `datetime`

**Важно!** Объект изображения может быть создан, но не может быть
изменён.


### Тип размера `size_type`

