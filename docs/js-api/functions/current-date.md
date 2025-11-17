---
title: function currentDate()
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/functions/current-date
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function currentDate()
---

<!-- Бейджи: Code -->

# function currentDate()

Содержание раздела

* [Примеры значений](#primery-znacheniy56)

# function currentDate()

Обновлено 15 декабря 2023

[![](/assets/js-api/functions/current-date/Code.png)
Code](../../overview.md)

Возвращает объект `moment.js` с текущей датой.

Обратите внимание, что функция определена в системном модуле.

[Подробнее о системных модулях](../../project/sys-modules.md)





##### Примеры значений

```
script:
            if (!$client.firstEntrance) {
                $temp.startConversation = "/Main"
            } else {
                var interval = currentDate().valueOf() - $session.lastActiveTime.valueOf();
                if (interval > 86400000) {
                    $temp.startConversation = "/Menu"
                }
            }
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней