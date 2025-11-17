---
title: function getEntity(text)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/get-entity
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function getEntity(text)
---

<!-- Бейджи: Code | Brain -->

# function getEntity(text)

Содержание раздела

* [Параметры](#parametry14)
* [Параметры](#parametry15)

# function getEntity(text)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/get-entity/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/get-entity/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет вызов в NLU-сервис Brain и возвращает все заданные значения сущности в виде массива.



##### Параметры

Метод принимает в качестве аргумента имя сущности в виде строки `string`:

```
$caila.getEntity("Name");
```

В качестве ответа передается JSON с набором значений, которые может принимать сущность.



##### Параметры

Рассмотрим пример вывода значений сущности. Предварительно зададим сущность `@Yes` в справочнике укажем набор паттернов:

```
[ну] [конечно|все|все|вроде|пожалуй|возможно] (да|даа|lf|ага|агась|точно|угу|верно|ок|ok|окей|окай|okay|оке|именно|подтвержд*|йес) [да|конечно|конешно|канешна|все|все|вроде|пожалуй|возможно]
```

Сценарий:

```
state:
    q!: да
    script:
        $reactions.answer(JSON.stringify($caila.getEntity("Yes")));
```

В качестве ответа будет передан JSON:

```
{
   "name":"Yes",
   "id":52502,
   "records":{
      "id":902002,
      "values":[
         "[ну конечно|все|все|вроде|пожалуй|возможно (да|даа|lf|ага|агась|точно|угу|верно|ок|ok|окей|окай|okay|оке|именно|подтвержд*|йес) да|конечно|конешно|канешна|все|все|вроде|пожалуй|возможно"
      ]
   }
]
}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней