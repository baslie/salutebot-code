---
title: function put(url, settings)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/http/put
reading_time: 1
badges:
- Code
breadcrumbs:
- function put(url, settings)
---

<!-- Бейджи: Code -->

# function put(url, settings)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/http/put/Code.png)
Code](../../../overview.md)

Эквивалентен вызову `$http.query(url, settings)`, при условии, что `settings.method == 'PUT'`.

Может содержать сторонний адрес.

В одном запросе можно совершить максимум 15 вызовов. При превышении количества вызовов возращается ошибка:

```
{
    "error": "Callback limit reached",
    "status": -1,
    "isOk": false
}
```

Адрес может быть как абсолютным, так и относительным. Для использования относительного адреса, необходимо задать базовый адрес с помощью метода [`$http.config(settings)`](config.md).

Подробнее о работе с [`$http.query(url, settings)`](query.md)

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней