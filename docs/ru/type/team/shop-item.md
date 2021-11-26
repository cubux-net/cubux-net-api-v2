Тип `Cubux.ShopItem`
====================

Позиция в списке покупок.

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK        | `uuid`      | UUID
`alternative_goods`  | `Array:uuid` | Список UUID альтернативных товаров [`Cubux.Good`][Cubux.Good]
`count`              | `float`     | Количество
`description`        | `string`    | Комментарий, описание
`good_uuid` **\*1)** | `uuid`      | UUID товара [`Cubux.Good`][Cubux.Good] из справочника
`in_cart`            | `boolean`   | Статус "уже в корзине"
`shop_list_uuid` **\*1)** | `uuid` | UUID списка покупок
`sort`               | `uint16`    | Порядок сортировки. Применяется как к основным позициям (`alternative_to_uuid` есть NULL), так и к альтернативным (`alternative_to_uuid` есть UUID)

**\*1)** Поля `good_uuid` и `shop_list_uuid`
можно назначать только при создании объекта, но нельзя менять позже.
Если необходимо какое-либо перемещение позиций, то реализуйте его путем
удаления старой и создания новой позиции.


[Cubux.Good]: ./good.md
