---
title: $client
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/variables/client
description: Переменная $client для JS API для смартапов | Переменная `$client` для
  JS API в Code для смартапов
reading_time: 1
badges:
- Code
breadcrumbs:
- $client
---

<!-- Бейджи: Code -->

# $client

Содержание раздела

* [Примеры значений](#primery-znacheniy99)

# $client

Обновлено 16 июня 2025

[![](/assets/js-api/variables/client/Code.png)
Code](../../overview.md)

Объект для сохранения постоянных данных о клиенте.

После завершения всех реакций, структура `$client` сохраняется во внутренней базе данных. Не имеет особых полей.

[Существует ограничение на объем хранящихся данных в объектe `$client`](../overflow-session-client-data.md). При превышении лимита текущий сценарий прерывается, смартап перестает отвечать клиенту.





##### Примеры значений

```
state: Welcome
    script:
      $context.session = {}
      var $session = $context.session;
      $client.welcome = true;
```

```
if: !$client.registered
            go!: /Registration/Start
        else:
            go!: /Welcome
```

Если клиент был неактивен в течение 12 месяцев, его контекстные данные будут очищены.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней