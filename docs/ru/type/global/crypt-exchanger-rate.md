Тип `Cubux.CryptExchangerRate`
==============================

Курс обмена криптовалюты на бирже.

Объект со следующими полями:

Поле     | Тип            | Описание
-------- | -------------- | --------
`x_uuid` | `uuid`         | UUID биржи [`Cubux.CryptExchanger`][Cubux.CryptExchanger]
`from`   | `string`       | Код исходной валюты [`Cubux.Currency`][Cubux.Currency]
`to`     | `string`       | Код целевой валюты [`Cubux.Currency`][Cubux.Currency]
`coeff`  | `float`        | Отношение целевой валюты к исходной
`time`   | `timestamp-ms` | Время формирования отношения

_N_ единиц валюты `from` есть (_N_ * `coeff`) единиц валюты `to`:

                        to
    N [from] * coeff [ ---- ] = M [to]
                       from


[Cubux.Currency]: ../global/currency.md
[Cubux.CryptExchanger]: ./crypt-exchanger.md
