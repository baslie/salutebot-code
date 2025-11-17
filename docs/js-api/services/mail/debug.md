---
title: function debug(enabled)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/mail/debug
description: function debug(enabled) для смартапов | Функция function debug(enabled)
  для JS API
reading_time: 1
badges:
- Code
breadcrumbs:
- function debug(enabled)
toc:
- title: Примеры значений
  level: 2
  id: primery-znacheniy77
---

<!-- Бейджи: Code -->

# function debug(enabled)

Содержание раздела

* [Примеры значений](#примеры-значений)

# function debug(enabled)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/mail/debug/Code.png)
Code](../../../overview.md)

Включить/выключить (`true/false`, соответственно) debug-режим для объекта `$mail`.

При включенном режиме в лог выводится информация об отправленных сообщениях.

## Примеры значений

```
init:
  $mail.debug(true);
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней