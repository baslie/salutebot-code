---
title: function currentTime()
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/jsapi/current-time
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function currentTime()
---

<!-- Бейджи: Code -->

# function currentTime()

Содержание раздела

* [Примеры значений](#primery-znacheniy69)

# function currentTime()

Обновлено 15 декабря 2023

[![](/assets/js-api/services/jsapi/current-time/Code.png)
Code](../../../overview.md)

Возвращает текущее время системы в миллисекундах.

Значение может быть переопределено в тестах.



##### Примеры значений

```
state: CurrentTime
        q!: который час
        script:
            var timestamp = moment($jsapi.currentTime());
            $temp.time = timestamp.format("HH:mm:ss");
        a: Сейчас: {{ $temp.time }}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней