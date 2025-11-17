---
title: Типы событий event
source_url: https://developers.sber.ru/docs/ru/va/code/response/events-table
reading_time: 1
badges:
- Code
breadcrumbs:
- Типы событий event
toc:
- title: Общие события
  level: 2
  id: obshie-sobytiya2
- title: События STS классификатора
  level: 2
  id: sobytiya-sts-klassifikatora2
---

<!-- Бейджи: Code -->

# Типы событий event

Содержание раздела

* [Общие события](#общие-события)
* [События STS классификатора](#события-sts-классификатора)

# Типы событий event

Обновлено 15 декабря 2023

[![](/assets/response/events-table/Code.png)
Code](../overview.md)

[`event`](../sa-dsl/tags/declarative-tags.md#event) — реакция на событие, приходящие от ассистента, аккаунта или проекта.





## Общие события

| **event** | Описание |
| --- | --- |
| `sessionDataSoftLimitExceeded` | [достижение soft лимита сохранения данных в объект `$session`](../js-api/overflow-session-client-data.md) |
| `clientDataSoftLimitExceeded` | [достижение soft лимита сохранения данных в объект `$client`](../js-api/overflow-session-client-data.md) |
| `sessionDataHardLimitExceeded` | [достижение hard лимита сохранения данных в объект `$session`](../js-api/overflow-session-client-data.md) |
| `clientDataHardLimitExceeded` | [достижение hard лимита сохранения данных в объект `$client`](../js-api/overflow-session-client-data.md) |






При превышении лимита текущий сценарий прерывается, смартап перестает отвечать клиенту. Для того, чтобы сценарий не прерывался, необходимо обрабатывать переполнение данных объектов `$session` и `$client` в сценарии.

В списке доступны следующие системные события:

* Превышен лимит на время обработки запроса (timeLimit). Событие срабатывает по таймауту классификации запроса, если время работы классификатора превысит 10 секунд.
* Превышен размер входящего сообщения (lengthLimit). Событие срабатывает в сценарии, если запрос (сообщение) пользователя превысил 400 символов. Если такое событие не предусмотрено в сценарии, то при отправке пользователем слишком большого текста, чат-бот по умолчанию промолчит.

Подробнее об ограничениях читайте в разделе [Превышение лимита объектов $session и $client](../js-api/overflow-session-client-data.md#лимиты).

## События STS классификатора

| **event** | Описание |
| --- | --- |
| `match` | отправленный текст распознан |
| `noMatch` | отправленный текст не распознан |
| `timeLimit` | превышение лимита на время обработки запроса |
| `lengthLimit` | превышение лимита на количество символов |

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней