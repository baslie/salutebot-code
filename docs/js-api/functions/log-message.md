---
title: function log(message)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/functions/log-message
description: function log(message) для смартапов | Функция function log(message) для
  JS API
reading_time: 1
badges:
- Code
breadcrumbs:
- function log(message)
---

<!-- Бейджи: Code -->

# function log(message)

Содержание раздела

* [Параметры](#parametry11)
* [Примеры значений](#primery-znacheniy57)

# function log(message)

Обновлено 15 декабря 2023

[![](/assets/js-api/functions/log-message/Code.png)
Code](../../overview.md)

Функция выводит сообщение в лог сервера и используется для отладки.



##### Параметры

Функция может принимать аргументы различных типов.

Если передать функции `json`-объект, то он будет выведен в лог полностью с распечаткой всех полей.





##### Примеры значений

Пример использования для вывода текущего значения переменных:

```
// $session.codes = ["XeZ4","o09E","sadL"];
state: GetPromoCode
    q!: хочу получить промокод
    a: Твой промокод: {{ $session.codes.splice(0,1) }}
    script:
         $jsapi.log("Осталось промокодов: " + $session.codes.length);
```

Ожидаемый вывод в логах сервера:

```
2018-11-15 14:49:43,123 INFO [js] - Осталось промокодов: 2
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней