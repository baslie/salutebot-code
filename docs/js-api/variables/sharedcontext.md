---
title: $sharedContext
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/variables/sharedcontext
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
breadcrumbs:
- $sharedContext
toc:
- title: Структура объекта
  level: 2
  id: struktura-obekta
- title: Лимиты
  level: 2
  id: limity
- title: Пример
  level: 2
  id: primer
---

# $sharedContext

Содержание раздела

* [Структура объекта](#структура-объекта)
* [Лимиты](#лимиты)
* [Пример](#пример)

# $sharedContext

Обновлено 16 июня 2025

Объект, который хранит данные сессии неаутентифицированного пользователя и обеспечивает доступ к ним после аутентификации.

Идентификация пользователя до авторизации выполняется на основе данных об устройстве, на котором запущен смартап. Таким образом данные из переменной `$sharedContext` сохраняются только в рамках устройства.

Переменная недоступна в тестовом виджете. Для тестирования Chat App используйте [эмулятор](https://developers.sber.ru/docs/ru/va/chat/testing).

## Структура объекта

id
uuid
required

Идентификатор записи

userId
uuid
required

Идентификатор пользователя. Не изменяется после авторизации

projectShortName
string
required

Идентификатор проекта

sharedData
jsonb

Контекстные данные запущенного смартапа в формате произвольного JSON-объекта

accountId
uuid
required

Идентификатор пространства

## Лимиты

Размер объекта `$sharedContext` ограничен мягким и жестким лимитам в 100 Кб и 1000 Кб соотвественно.

При достижении мягкого лимита в сценарий передается событие `sharedDataSoftLimitExceeded`:

```
event: sharedDataSoftLimitExceeded
```

При этом данные контекста продолжат сохраняться до достижения жесткого лимита. При достижении жесткого лимита в сценарий передается событие `sharedDataHardLimitExceeded`:

```
event: sharedDataHardLimitExceeded
```

При этом данные перестают сохраняться в объекте `$sharedContext`.

## Пример

```
theme: /

    state:
        q: * *start
        go!: /start

    state: start
        q!: *
        script:
            $sharedContext.sharedData = $parseTree.text    // сохраняем данные сессии
        a: Вы сказали: {{$sharedContext.text}}.

    state:
        event: sharedDataSoftLimitExceeded    // обрабатываем событие о достижении мягкого лимита
        script:
            delete $sharedContext.sharedData;               // при достижении мягкого лимита данные активного смартапа удаляются
```

Если клиент был неактивен в течение 12 месяцев, его контекстные данные будут очищены.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней