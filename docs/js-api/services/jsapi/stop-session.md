---
title: function stopSession()
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/jsapi/stop-session
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function stopSession()
toc:
- title: Примеры значений
  level: 2
  id: primery-znacheniy75
---

<!-- Бейджи: Code -->

# function stopSession()

Содержание раздела

* [Примеры значений](#примеры-значений)

# function stopSession()

Обновлено 15 декабря 2023

[![](/assets/js-api/services/jsapi/stop-session/Code.png)
Code](../../../overview.md)

Метод `$jsapi.stopSession()` завершает сессию.

Данные в [`$session`](../../variables/session.md) очищаются сразу при вызове метода. Текущий вопрос пользователя и ответ ассистента попадают в предыдущую сессию. Последующие запросы записываются в новую сессию.

Метод [не закрывает окно смартапа](https://developers.sber.ru/docs/ru/va/chat/script/start-stop/close-app).

## Примеры значений

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