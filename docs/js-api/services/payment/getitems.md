---
title: function getItems()
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/payment/getitems
reading_time: 1
breadcrumbs:
- function getItems()
---

# function getItems()

Обновлено 15 декабря 2023

Функция `$payment.getItems()` возвращает список товаров, добавленных в счет.

```
script: $reactions.answer(JSON.stringify($payment.getItems()));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней