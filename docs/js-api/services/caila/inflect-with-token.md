---
title: function inflect(text, tag declension, token)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/inflect-with-token
description: function inflect(text, tag declension, token) для смартапов | Функция
  function inflect(text, tag declension, token) для JS API
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function inflect(text, tag declension, token)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis29
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii29
---

<!-- Бейджи: Code | Brain -->

# function inflect(text, tag declension, token)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function inflect(text, tag declension, token)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/inflect-with-token/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/inflect-with-token/Brain.png)
Brain](../../../nlp/overview.md)

Склоняет текст в требуемый формат. Метод используется для обращения к стороннему обученному классификатору при помощи API-ключа.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки и API-токен в виде строк `string`, тег склонения `tag`:

```
$caila.inflect("text", ["tag"], "token")
```

[Подробнее о получении API-ключа](../../../nlp/api/overview.md#section/Autentifikaciya)

[Возможные значения `tag declension`](inflect.md#padezh2)

В качестве ответа передается строка с фразой в требуемом падеже.



#### Использование в сценарии

```
    state:
        q!: inflectWithToken
        script:
            $reactions.answer($caila.inflectWithToken("Мария дала книгу", ["voct"], "token"))
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней