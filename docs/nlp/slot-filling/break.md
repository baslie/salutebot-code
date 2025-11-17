---
title: Прерывание слот-филлинга в Code и Brain
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/slot-filling/break
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- Прерывание слот-филлинга
toc:
- title: Прерывание по интенту
  level: 2
  id: preryvanie-po-intentu2
---

<!-- Бейджи: Code | Brain -->

# Прерывание слот-филлинга в Code и Brain

Содержание раздела

* [Прерывание по интенту](#прерывание-по-интенту)

# Прерывание слот-филлинга в Code и Brain

Обновлено 15 декабря 2023

[![](/assets/nlp/slot-filling/break/Code.png)
Code](../../overview.md)[![](/assets/nlp/slot-filling/break/Brain.png)
Brain](../overview.md)

Условия прерывания слот-филлинга задаются в файле [`chatbot.yaml`](../../project/configuration-file.md) в разделе [`injector`](../../project/configuration-file.md#секция-injector):

```
injector:
    slotfilling:
        maxSlotRetries: 1
        stopOnAnyIntent: true
        stopOnAnyIntentThreshold: 0.2
```

Где:

* `maxSlotRetries` — количество попыток для одного слота. Если пользователь ответил указанное количество раз и слот не был заполнен, процесс слот-филлинга прерывается. Последняя фраза пользователя обрабатывается в сценарии смартапа.
* `stopOnAnyIntent` — параметр прерывания слот-филлинга по интенту. Принимает значения `true` или `false`.
* `stopOnAnyIntentThreshold` — параметр соответствия, задающий минимально необходимую схожесть фразы с одним из классов. Является параметром прерывания слот-филлинга по интенту.

## Прерывание по интенту

Если `stopOnAnyIntent: true` и запросу клиента соответствует интент с параметром `confidence` выше, чем `stopOnAnyIntentThreshold`, слот-филлинг прерывается по интенту.

Параметр `confidence` — степень уверенности Code в том, что введенная фраза относится к определенному интенту.

Нужно учитывать контекст начала слот-филлинга. Например, если при прерывании в стейт с соответствующим интентом невозможно попасть (например, тег [`intent`](../../sa-dsl/tags/intents-tags.md) не глобальный), то запрос попадет в тег [`event!`](../../sa-dsl/tags/declarative-tags.md#event) согласно правилу `noMatch`.

Если параметры для прерывания в конфигурационном файле `chatbot.yaml` не указаны, слот-филлинг прерывается согласно параметрам по умолчанию:

```
injector:
    slotfilling:
        maxSlotRetries: 2
        stopOnAnyIntent: false
        stopOnAnyIntentThreshold: 0.2
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней