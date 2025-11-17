---
title: function entitiesLookup(text)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/entities-lookup
description: function entitiesLookup(text) для смартапов | Функция function entitiesLookup(text)
  для JS API
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function entitiesLookup(text)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis24
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii24
---

<!-- Бейджи: Code | Brain -->

# function entitiesLookup(text)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function entitiesLookup(text)

Обновлено 18 июля 2024

[![](/assets/js-api/services/caila/entities-lookup/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/entities-lookup/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет поиск сущностей в переданном тексте.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки в виде строки `string`, а также флаг `show all`. При значении флага:

* `true` — в ответе будут переданы все найденные гипотезы.
* `false` — в ответе будут переданы наиболее вероятные гипотезы для каждой из сущностей, найденных в тексте.

```
$caila.entitiesLookup("text@entities.ru", true)
```

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
        q!: entitiesLookup
        script:
            $reactions.answer(JSON.stringify($caila.entitiesLookup("test@test.ru", true)));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней