Курсы криптовалют
=================

```
GET /api/v4/crypto/exchange-rate
```

В параметрах запроса допустимы следующие поля для фильтрации результата:

Поле | Тип | Описание
---- | --- | --------
`filter` | JSON | Набор фильтров. По умолчанию нет фильтрации. См. ниже.
`after` | `timestamp-ms` | Выводить только отношения, изменившиеся позднее указанного времени (не включая).

### `filter` JSON

Параметр `filter` может принимать JSON, содержащий массив из отдельных
альтернативных фильтров, которые в конце будут объединены условием "ИЛИ".

Поле | Тип | Описание
---- | --- | --------
`filter[i].uuid` | `uuid` | **Обязательно** UUID биржи [`Cubux.CryptExchanger`][Cubux.CryptExchanger]
`filter[i].pairs` | `Array:Array:string` | Список криптовалютных пар, для которых необходимо получить отношения.
`filter[i].after` | `timestamp-ms` | Выводить только отношения, изменившиеся позднее указанного времени (не включая).

Если указаны `filter[i].after` и `after`, то для `filter[i]` будет
использоваться значение `filter[i].after`.

Если указан `after`, но в `filter[i]` не указан `filter[i].after`, то
для `filter[i]` будет использоваться значение `after`.

Если `filter` пуст, то `after` будет использоваться отдельно для всех.


## Ответ

**Важно:** В ответе отдаются только непосредственные отношения курсов,
которые есть в распоряжении сервера.

Ответ содержит объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`items` | `Array:`[`Cubux.CryptExchangerRate`][Cubux.CryptExchangerRate] | Данные об отношениях курсов

## Пример

(переносы добавлены для читабельности)

```
GET /api/v2/crypto/exchange-rate?filter=[
      {
        "uuid": "ac5bec9d-235a-4869-9c57-600c3928a13e",
        "pairs": [
          ["BTC", "USDT"],
          ["ETH", "EUR"]
        ]
      }
    ]
```

Ответ:

```
{
  "items": [
    {
      "exchanger_uuid": "ac5bec9d-235a-4869-9c57-600c3928a13e",
      "from_code": "BTC",
      "to_code": "USDT",
      "coeff": 62620.93,
      "time": 1634618387604
    },
    {
      "exchanger_uuid": "ac5bec9d-235a-4869-9c57-600c3928a13e",
      "from_code": "ETH",
      "to_code": "EUR",
      "coeff": 3293.83,
      "time": 1634618387604
    }
  ]
}
```


[Cubux.CryptExchanger]: ../../type/global/crypt-exchanger.md
[Cubux.CryptExchangerRate]: ../../type/global/crypt-exchanger-rate.md
