---
title: $fetch
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/fetch/overview
description: $fetch | Разработка приложений для виртуального ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- fetch
---

<!-- Бейджи: Code -->

# $fetch

Обновлено 15 декабря 2023

[![](/assets/js-api/services/fetch/overview/Code.png)
Code](../../../overview.md)

Сервис для выполнения асинхронных запросов к сценарию на внешнем сервере.

Сервис подключен по умолчанию во все новые проекты. Вы также можете подключить его в существующие проекты, в файле `chatbot.yaml`:

```
scriptsPreLoad:
  global:
    - /jsapi/fetch.js
```

Несколько последовательных запросов к внешнему серверу можно сделать с помощью последовательного вызова методов `then()` и `catch()`.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней