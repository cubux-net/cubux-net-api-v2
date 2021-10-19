Тип `Cubux.CryptExchangerRate`
==============================

Курс обмена криптовалюты на бирже.

Объект со следующими полями:

Поле             | Тип            | Описание
---------------- | -------------- | --------
`exchanger_uuid` | `uuid`         | UUID биржи [`Cubux.CryptExchanger`][Cubux.CryptExchanger]
`from_code`      | `string`       | Код исходной криптовалюты [`Cubux.CryptCurrency`][Cubux.CryptCurrency]
`to_code`        | `string`       | Код целевой криптовалюты [`Cubux.CryptCurrency`][Cubux.CryptCurrency]
`coeff`          | `float`        | Отношение целевой валюты к исходной
`time`           | `timestamp-ms` | Время формирования отношения

_N_ единиц валюты `from_code` есть (_N_ * `coeff`) единиц валюты
`to_code`:

                             to_code
    N [from_code] * coeff [ --------- ] = M [to_code]
                            from_code


[Cubux.CryptCurrency]: ../global/crypt-currency.md
[Cubux.CryptExchanger]: ./crypt-exchanger.md
