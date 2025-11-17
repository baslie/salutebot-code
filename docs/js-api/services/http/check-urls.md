---
title: function checkUrls(method, urls, findFirst)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/http/check-urls
reading_time: 1
badges:
- Code
breadcrumbs:
- function checkUrls(method, urls, findFirst)
---

<!-- Бейджи: Code -->

# function checkUrls(method, urls, findFirst)

Содержание раздела

* [Синтаксис](#sintaksis36)
* [Примеры значений](#primery-znacheniy63)

# function checkUrls(method, urls, findFirst)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/http/check-urls/Code.png)
Code](../../../overview.md)

Метод проверки доступности сайтов. Возвращает список: из одного или нескольких сайтов, в зависимости от флага `findFirst`.



##### Синтаксис

```
$http.checkUrls(method: HEAD|POST|GET, urls: [''..], findFirst: true|false)
```





##### Примеры значений

```
state:
        q!: *
        script:
            $temp.url = $http.checkUrls("HEAD", ['http://orrp.ru:8013/live_192', 'http://hosting.express.net.ua:13000', 'http://nashe.streamr.ru/rock-128.mp3'], true);
        a: {{ $temp.url }}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней