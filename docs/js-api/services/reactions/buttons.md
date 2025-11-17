---
title: function buttons(arg)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/reactions/buttons
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Chat App
breadcrumbs:
- function buttons(arg)
---

<!-- Бейджи: Code | Chat App -->

# function buttons(arg)

Содержание раздела

* [Примеры значений](#primery-znacheniy93)

# function buttons(arg)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/reactions/buttons/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/reactions/buttons/ChatApp.png)
Chat App](https://developers.sber.ru/docs/ru/va/chat/title-page)

Функция позволяет добавлять в ответ кнопки. Функция принимает объект, который состоит из следующих параметров:

* `text` — название кнопки;
* `transition`, `url` — путь перехода при клике на кнопку.



##### Примеры значений

```
script: $reactions.buttons('Одна кнопка');
$reactions.buttons(['Одна кнопка', 'И другая в том же ряду']);
$reactions.buttons({ button: { text: 'Отправить контактные данные', request_contact: true } });
$reactions.buttons({ text: 'Кнопка с переходом', transition: '/state' });
$reactions.buttons([{ text: 'Кнопка 1' }, { text: 'Кнопка 2', request_contact: true }]);
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней