---
title: function entitiesLookupWithToken(text, token)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/entities-lookup-with-token
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function entitiesLookupWithToken(text, token)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis25
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii25
---

<!-- Бейджи: Code | Brain -->

# function entitiesLookupWithToken(text, token)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function entitiesLookupWithToken(text, token)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/entities-lookup-with-token/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/entities-lookup-with-token/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет поиск сущностей в переданном тексте. Метод используется для обращения к стороннему обученному классификатору при помощи API-ключа.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки и API-ключ к стороннему обученному классификатору в виде строк `string`, флаг `show all`. При значении флага:

* `true` — в ответе будут переданы все найденные гипотезы.
* `false` — в ответе будут переданы наиболее вероятные гипотезы для кажажой из сущностей, найденных в тексте.

```
$caila.entitiesLookup("text@entities.ru", true, "token")
```

[Подробнее о получении API-ключа](../../../nlp/api/overview.md#section/Autentifikaciya)

В качестве ответа передается JSON с найденными сущностями во фразе. Результат поиска сущностей во фразе `text@entities.ru` с выводом всех гипотез:

```
{
    "text": "text@entities.ru",
    "entities": {
        "default": true,
        "entity": "duckling.email", //найденная сущность
        "startPos": 0, //позиция слова во фразе
        "endPos": 16,
        "text": "text@entities.ru",
        "value": "text@entities.ru",
        "system": true
    }
}
```





#### Использование в сценарии

```
state:
   q!: entitiesLookupWithToken
   script:
      $reactions.answer(JSON.stringify($caila.entitiesLookupWithToken("test@test.ru", true, "token")));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней