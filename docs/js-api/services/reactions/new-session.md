---
title: function newSession(arg)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/reactions/new-session
reading_time: 1
badges:
- Code
breadcrumbs:
- function newSession(arg)
---

<!-- Бейджи: Code -->

# function newSession(arg)

Содержание раздела

* [Примеры значений](#primery-znacheniy95)

# function newSession(arg)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/reactions/new-session/Code.png)
Code](../../../overview.md)

Метод предназначен для явного создания новой сессии из скрипта.



##### Примеры значений

```
script: if (!$context.testContext && !$request.data.newSession) {
    if ($parseTree) {
        $reactions.newSession({ message: $parseTree.text, data: { newSession: true } });
    } else {
        $reactions.newSession({ message: '/start', data: { newSession: true } });
    }
}
```

```
state: reset
        q!: reset
        script:
            $reactions.newSession({message: "/start", data: $request.data});
```

[Подробнее о сессиях в платформе Code](../../session-lifetime-control.md)

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней