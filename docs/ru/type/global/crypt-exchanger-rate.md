Тип `Cubux.CryptExchangerRate`
==============================

Курс обмена криптовалюты на бирже.

Объект со следующими полями:

Поле             | Тип            | Описание
---------------- | -------------- | --------
`exchanger_uuid` | `uuid`         | UUID биржи [`Cubux.CryptExchanger`][Cubux.CryptExchanger]
`from_code`      | `string(3)`    | Код исходной валюты (см. [валюты][])
`to_code`        | `string(3)`    | Код целевой валюты
`coeff`          | `decimal(.10)` | Отношение целевой валюты к исходной
`date`           | `date`         | Дата формирования отношения

_N_ единиц валюты `from_code` есть (_N_ * `coeff`) единиц валюты
`to_code`:

                             to_code
    N [from_code] * coeff [ --------- ] = M [to_code]
                            from_code


[Cubux.CryptExchanger]: ./crypt-exchanger.md
[валюты]: ../global/currency.md
