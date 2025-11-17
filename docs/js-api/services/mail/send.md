---
title: function send(mailRequest)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/mail/send
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function send(mailRequest)
toc:
- title: Примеры значений
  level: 2
  id: primery-znacheniy78
---

<!-- Бейджи: Code -->

# function send(mailRequest)

Содержание раздела

* [Примеры значений](#примеры-значений)

# function send(mailRequest)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/mail/send/Code.png)
Code](../../../overview.md)

Более гибкий метод отправки сообщения, чем `sendMessage(address, subject, body)`. Метод не требует конфигурирования — все параметры передаются в `mailRequest` в следующем виде:

```
{
    from: "test@test.com",
    hiddenCopy: ["hidden@test.com"],
    to: ["recipient@test.com"],
    subject: "any subject",
    content: "any body",
    smtpHost: "...",
    smtpPort: "...",
    user: "...",
    password: "..."
}
```

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
            $mail.send({
                from: "asd@asd.com",
                hiddenCopy: [],
                to: ["recipient@cscs.com"],
                subject: "Subject",
                content: "Message",
                smtpHost: "localhost",
                smtpPort: "25000",
                user: "user",
                password: "password"
            });
```

Доступные порты:

* 80
* 443
* 465
* 587
* 2443
* 6443
* 8080
* 8443
* 9443

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней