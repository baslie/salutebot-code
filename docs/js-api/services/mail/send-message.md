---
title: function sendMessage(address, subject, body)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/mail/send-message
reading_time: 1
badges:
- Code
breadcrumbs:
- function sendMessage(address, subject, body)
toc:
- title: Примеры значений
  level: 2
  id: primery-znacheniy79
---

<!-- Бейджи: Code -->

# function sendMessage(address, subject, body)

Содержание раздела

* [Примеры значений](#примеры-значений)

# function sendMessage(address, subject, body)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/mail/send-message/Code.png)
Code](../../../overview.md)

Отправляет сообщение на указанный адрес с указанной темой и телом сообщения.

Параметры:

* `address` — адрес электронной почты;
* `subject` — тема письма;
* `body` — тело сообщения.

Возвращает объект вида:

```
{"status":"OK"}
```

Возможные значения поля `status`:

* `OK` — письмо успешно отправлено;
* `UNABLE_TO_CONNECT` — ошибка подключения;
* `INCORRECT_ADDRESS` — указанный адрес не существует.

## Примеры значений

```
state:
        q!: *
        script:
            $mail.sendMessage("coco@coco.com", "message subject", "message body");
            $reactions.answer("Отправил почту", $context);
```

Запрос на отправку письма отправляется с заголовком `contentType: "text/html"`. В тексте письма (содержание `body`) можно использовать html-теги.

Обратите внимание: отображение письма с форматированием html также зависит от почтового клиента, в котором будет открыто письмо и от того, какие теги он поддерживает.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней