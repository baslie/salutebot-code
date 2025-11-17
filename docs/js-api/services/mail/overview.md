---
title: $mail
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/mail/overview
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- Как задать конфигурацию
---

<!-- Бейджи: Code -->

# $mail

Обновлено 15 декабря 2023

[![](/assets/js-api/services/mail/overview/Code.png)
Code](../../../overview.md)

Сервис используется для отправки e-mail сообщений из сценария смартапа.

Встроенный сервис `$mail` включает методы:

* [`debug`](debug.md);
* [`send`](send.md);
* [`sendMessage`](send-message.md).

Конфигурация SMTP-сервера задается в секции `injector` файла `chatbot.yaml`:

```
injector:
    smtp:
        host: # хост SMTP-сервера
        port: 25000 # порт SMTP-сервера
        from: example@sberdevices.ru # отправитель
        user: user # пользователь SMTP-сервера
        password: password # пароль SMTP-сервера
        hiddenCopy: ["myaddres@sberdevices.ru"] # необязательный массив адресов, для отправки скрытой копии
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

Также можно выполнить конфигурацию, используя функцию:

```
$mail.config (smtpHost, smtpPort, user, password, from, hiddenCopy)
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней