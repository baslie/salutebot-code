---
title: function check(method, urls)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/http/check
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function check(method, urls)
---

<!-- Бейджи: Code -->

# function check(method, urls)

Содержание раздела

* [Синтаксис](#sintaksis35)
* [Примеры значений](#primery-znacheniy62)

# function check(method, urls)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/http/check/Code.png)
Code](../../../overview.md)

Метод проверки доступности сайтов. Возвращает один сайт.



##### Синтаксис

```
$http.check(method: HEAD|POST|GET, urls: [''..])
```





##### Примеры значений

```
state:
        q!: *
        script:
            $temp.url = $http.check("HEAD", ['http://orrp.ru:8013/live_192', 'http://hosting.express.net.ua:13000', 'http://nashe.streamr.ru/rock-128.mp3']);
        a: {{ $temp.url }}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней