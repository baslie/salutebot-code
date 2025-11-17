---
title: function dateForZone(zone, format)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/jsapi/date-for-zone
description: function dateForZone(zone, format) для смартапов | Функция function dateForZone(zone,
  format) для JS API
reading_time: 1
badges:
- Code
breadcrumbs:
- function dateForZone(zone, format)
---

<!-- Бейджи: Code -->

# function dateForZone(zone, format)

Содержание раздела

* [Примеры значений](#primery-znacheniy70)

# function dateForZone(zone, format)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/jsapi/date-for-zone/Code.png)
Code](../../../overview.md)

Метод предназначен для получения текущей даты в заданном формате.

Дата прописывается строкой, используйте [шаблон синтаксиса формата даты](https://docs.oracle.com/javase/tutorial/i18n/format/simpleDateFormat.html) .

Тайм-зона прописывается согласно [классификации](https://garygregory.wordpress.com/2013/06/18/what-are-the-java-timezone-ids/) .



##### Примеры значений

```
log($jsapi.dateForZone("Europe/Moscow", "dd.MM"))

14:47:07.460 [main] INFO  js - 07.05
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней