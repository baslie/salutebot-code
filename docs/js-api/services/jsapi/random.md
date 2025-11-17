---
title: function random(max)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/jsapi/random
reading_time: 1
badges:
- Code
breadcrumbs:
- function random(max)
---

<!-- Бейджи: Code -->

# function random(max)

Содержание раздела

* [Примеры значений](#primery-znacheniy72)

# function random(max)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/jsapi/random/Code.png)
Code](../../../overview.md)

Генератор случайных чисел. Метод возвращает целочисленные значения от `0` до `max` (не включая `maх`).

Отличается от `Math.random()` тем, что возвращаемые им значения могут быть переопределены в тестах.

Метод является вспомогательным для функции `$reactions.random()`. Использовать его напрямую не рекомендуется.



##### Примеры значений

```
function getRandomGenre(music) {
    var id = $jsapi.random(5) + 1;
    var randomGenre = music[id];
    return randomGenre;
}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней