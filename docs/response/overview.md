---
title: Формат ответа приложения в Code
source_url: https://developers.sber.ru/docs/ru/va/code/response/overview
description: Формат ответа приложения в Code | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Chat App
breadcrumbs:
- Формат ответа
---

<!-- Бейджи: Code | Chat App -->

# Формат ответа приложения в Code

Обновлено 15 декабря 2023

[![](/assets/response/overview/Code.png)
Code](../overview.md)[![](/assets/response/overview/ChatApp.png)
Chat App](https://developers.sber.ru/docs/ru/va/chat/title-page)

В Code вы можете создавать сообщения различных типов:

* [текстовые](message-types.md#text);
* [подсказки в диалоге с пользователем](message-types.md#buttons);
* [изображения](message-types.md#image);
* [карточки](message-types.md#card);
* [списки](message-types.md#cardlist);
* [произвольные ответы](message-types.md#raw).

Произвольные ответы позволяют передавать [команды](https://developers.sber.ru/docs/ru/va/api/smartapp-api-commands) и [действия](https://developers.sber.ru/docs/ru/va/api/smartapp-api-actions), которые соответствуют протоколу SmartApp API.

Ответы сохраняются в массиве `$response.replies` , который содержит [строго типизированные элементы](message-types.md). Массив наполняется с помощью метода `$response.replies.push()`.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней