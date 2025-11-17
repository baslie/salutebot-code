---
title: $fetch.get(url, settings)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/fetch/get
reading_time: 1
badges:
- Code
breadcrumbs:
- fetch
- fetch
- $fetch.get(url, settings)
toc:
- title: Примеры
  level: 2
  id: primery1
---

<!-- Бейджи: Code -->

# $fetch.get(url, settings)

Содержание раздела

* [Примеры](#примеры)

# $fetch.get(url, settings)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/fetch/get/Code.png)
Code](../../../overview.md)

Возвращает данные с внешнего сервера.

Эквивалентен вызову `$fetch.query(url, settings)`, при условии, что `settings.method == 'GET'`.

Параметры:

* `url` — адрес сервера в виде строки, может содержать параметры, которые будут заполнены из поля `query`, переданного в параметре `settings`.
* `settings` — валидный JSON с параметрами запроса.

## Примеры

```
patterns:
    $city = (москв*:moscow/питер*:saint_petersburg) || converter = function($pt){return $pt.value.replace("_","%20");}

state: Weather
    q!: Сколько градусов в $city
    script:
        var q = $parseTree.value;
        var url = "https://api.apixu.com/v1/current.json?key=" + $injector.wheatherApiKey + "&q=" + q;
        var response = $fetch.get(url);
        if (response.isOk) {
            $temp.degree = response.data.current.temp_c;
        }
    a: Сейчас {{ $temp.degree }}°C.
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней