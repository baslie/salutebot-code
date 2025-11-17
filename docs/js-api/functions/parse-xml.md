---
title: function parseXml(xmlString)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/functions/parse-xml
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function parseXml(xmlString)
---

<!-- Бейджи: Code -->

# function parseXml(xmlString)

Содержание раздела

* [Примеры значений](#primery-znacheniy58)

# function parseXml(xmlString)

Обновлено 15 декабря 2023

[![](/assets/js-api/functions/parse-xml/Code.png)
Code](../../overview.md)

Преобразует переданный xml-текст в JSON-объект.



##### Примеры значений

```
script:
    var o = $jsapi.parseXml("<test><a>1</a><a>2</a></test>");
    log(o);
```

Распечатает следующий объект:

```
{ "test": { "a": [1, 2] } }
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней