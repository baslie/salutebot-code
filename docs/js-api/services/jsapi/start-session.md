---
title: function startSession()
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/jsapi/start-session
reading_time: 1
badges:
- Code
breadcrumbs:
- function startSession()
---

<!-- Бейджи: Code -->

# function startSession()

Содержание раздела

* [Примеры значений](#primery-znacheniy74)

# function startSession()

Обновлено 15 декабря 2023

[![](/assets/js-api/services/jsapi/start-session/Code.png)
Code](../../../overview.md)

Метод `$jsapi.startSession()` начинает новую сессию.

При этом данные в [`$session`](../../variables/session.md) очищаются сразу при вызове метода. Текущий вопрос пользователя и ответ ассистента попадают сразу в новую сессию.



##### Примеры значений

```
theme: /

    state: Приветствие
        q!: * *start
        q!: (привет|hello) *
        script:
            $jsapi.startSession();
        a: Здравствуйте! Чем я могу Вам помочь?

    state: Прощание
        q!: (пока|до свидания|bye) *
        script:
            $jsapi.stopSession();
        random:
            a: Всего доброго.
            a: До свидания!
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней