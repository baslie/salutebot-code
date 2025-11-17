---
title: function toPrettyString(obj)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/functions/to-pretty-string
description: function toPrettyString(obj) для смартапов | Функция function toPrettyString(obj)
  для JS API
reading_time: 1
badges:
- Code
breadcrumbs:
- function toPrettyString(obj)
---

<!-- Бейджи: Code -->

# function toPrettyString(obj)

Содержание раздела

* [Примеры значений](#primery-znacheniy59)

# function toPrettyString(obj)

Обновлено 15 декабря 2023

[![](/assets/js-api/functions/to-pretty-string/Code.png)
Code](../../overview.md)

Преобразует переданный объект в форматированный JSON-объект с отступами.

Тип возвращаемого значения: `string`.





##### Примеры значений

Можно использовать при логировании:

```
var customer = {
    firstName: 'John',
    lastName: 'Doe',
    id: 5566,
    cart: [
        { itemName: 'Удочка', price: 432 },
        { itemName: 'Леска', price: 34 },
    ],
};
```

Сравните примеры логирования объектов с использованием `toPrettyString` и без:

* `log(customer)`

```
log(customer):
{"firstName":"John","lastName":"Doe","id":5566,"cart":[{"itemName":"Удочка","price":432},{"itemName":"Леска","price":34}]}
```

* `log(“Customer info:\n” + customer)`

```
[object Object]
```

* `log(toPrettyString(customer))`

```
{
    "firstName": "John",
    "lastName": "Doe",
    "id": 5566,
    "cart": [
        {
            "itemName": "Удочка",
            "price": 432
        },
        {
            "itemName": "Леска",
            "price": 34
        }
    ]
}
```

* `log(“Customer info:\n” + toPrettyString(customer))`

```
Customer info:
{
  "firstName": "John",
  "lastName": "Doe",
  "id": 5566,
  "cart": [
    {
      "itemName": "Удочка",
      "price": 432
    },
    {
      "itemName": "Леска",
      "price": 34
    }
  ]
}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней