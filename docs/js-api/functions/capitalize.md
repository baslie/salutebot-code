---
title: function capitalize(string)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/functions/capitalize
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function capitalize(string)
---

<!-- Бейджи: Code -->

# function capitalize(string)

Содержание раздела

* [Примеры значений](#primery-znacheniy55)

# function capitalize(string)

Обновлено 15 декабря 2023

[![](/assets/js-api/functions/capitalize/Code.png)
Code](../../overview.md)

Переводит первую букву переданной строки в заглавную. Используется для вывода имен и названий.



##### Примеры значений

```
script:
$reactions.answer(“Привет ” + capitalize($client.name));
```

```
a: Здравствуй {{ capitalize($client.name) }}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней