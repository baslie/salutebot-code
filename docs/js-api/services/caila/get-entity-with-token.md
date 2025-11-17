---
title: function getEntityWithToken(text, token)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/get-entity-with-token
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function getEntityWithToken(text, token)
---

<!-- Бейджи: Code | Brain -->

# function getEntityWithToken(text, token)

Содержание раздела

* [Параметры](#parametry16)
* [Параметры](#parametry17)

# function getEntityWithToken(text, token)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/get-entity-with-token/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/get-entity-with-token/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет вызов в NLU-сервис Brain и возвращает все заданные значения сущности в виде массива. Метод используется для обращения к стороннему обученному классификатору при помощи API-ключа.



##### Параметры

Метод принимает в качестве аргумента имя сущности и API-токен к стороннему обученному классификатору в виде строк `string`:

```
$caila.getEntityWithToken("Name", "token");
```

[Подробнее о получении API-ключа](../../../nlp/api/overview.md#section/Autentifikaciya)

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
        $reactions.answer(JSON.stringify($caila.getEntityWithToken("Yes", "API token")));
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