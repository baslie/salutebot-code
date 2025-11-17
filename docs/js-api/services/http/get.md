---
title: function get(url, settings)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/http/get
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function get(url, settings)
toc:
- title: Примеры значений
  level: 2
  id: primery-znacheniy65
---

<!-- Бейджи: Code -->

# function get(url, settings)

Содержание раздела

* [Примеры значений](#примеры-значений)

# function get(url, settings)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/http/get/Code.png)
Code](../../../overview.md)

Эквивалентен вызову `$http.query(url, settings)`, при условии, что `settings.method == 'GET'`.

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

## Примеры значений

```
patterns:
    $city = (москв*:moscow/питер*:saint_petersburg) || converter = function($pt){return $pt.value.replace("_","%20");}

state: Weather
    q!: Сколько градусов в $city
    script:
        var q = $parseTree.value;
        var url = "https://api.apixu.com/v1/current.json?key=" + $injector.wheatherApiKey + "&q=" + q;
        var response = $http.get(url);
        if (response.isOk) {
            $temp.degree = response.data.current.temp_c;
        }
    a: Сейчас {{ $temp.degree }}°C.
```

Подробнее о работе с [`$http.query(url, settings)`](query.md)

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней