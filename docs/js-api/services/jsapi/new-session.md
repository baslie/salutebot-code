---
title: function newSession(object)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/jsapi/new-session
reading_time: 1
badges:
- Code
breadcrumbs:
- function newSession(object)
---

<!-- Бейджи: Code -->

# function newSession(object)

Содержание раздела

* [Примеры значений](#primery-znacheniy71)

# function newSession(object)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/jsapi/new-session/Code.png)
Code](../../../overview.md)

Метод предназначен для явного создания новой сессии из скрипта.

Вы можете использовать [метод `$jsapi.startSession()` для начала новой сессии](start-session.md) и [метод `$jsapi.stopSession()` для завершения сессии](stop-session.md).





##### Примеры значений

```
state: reset
        q!: reset
        script:
            $jsapi.newSession({message: "/start", data: $request.data});
```

[Подробнее о сессиях: session lifetime control](../../session-lifetime-control.md)

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней