---
title: function conformWithToken(text, number, token)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/conform-with-token
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function conformWithToken(text, number, token)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis23
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii21
---

<!-- Бейджи: Code | Brain -->

# function conformWithToken(text, number, token)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function conformWithToken(text, number, token)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/conform-with-token/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/conform-with-token/Brain.png)
Brain](../../../nlp/overview.md)

Согласует слова с числительными. Метод используется для обращения к стороннему обученному классификатору при помощи API-ключа.



#### Синтаксис

Метод принимает в качестве аргумента текст и API-ключ к стороннему обученному классификатору в виде строк `string`, а также число для согласования `number`:

```
$caila.conform("text", number, "token")
```

[Подробнее о получении API-ключа](../../../nlp/api/overview.md#section/Autentifikaciya)

В качестве ответа передается строка с согласованной фразой.



#### Использование в сценарии

Запрос на согласование фразы:

```
    state:
        q!: conformWithToken
        script:
            $reactions.answer($caila.conform("хороший день", 2, "token"))
```

Ответ: `хороших дня`.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней