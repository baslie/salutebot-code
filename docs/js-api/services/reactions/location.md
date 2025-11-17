---
title: function location(ll, lg)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/reactions/location
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function location(ll, lg)
---

<!-- Бейджи: Code -->

# function location(ll, lg)

Содержание раздела

* [Примеры значений](#primery-znacheniy94)

# function location(ll, lg)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/reactions/location/Code.png)
Code](../../../overview.md)

Метод позволяет отправить местоположение в формате, поддерживаемом конкретным мессенджером.

В параметрах метода `(ll,lg)` передается широта и долгота.



##### Примеры значений

Используется для отправки координат, принимает широту и долготу:

```
state: Location
        q!: location
        script:
            $reactions.location(59.8762548, 30.3160391);
```

Эквивалентно использованию `$response.replies`:

```
$response.replies.push( {
            type: "location",
            lat: 59.8762548,
            lon: 30.3160391
        }
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней