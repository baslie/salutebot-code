---
title: function transition(transition)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/reactions/transition
reading_time: 1
badges:
- Code
breadcrumbs:
- function transition(transition)
---

<!-- Бейджи: Code -->

# function transition(transition)

Содержание раздела

* [Синтаксис](#sintaksis37)
* [Примеры значений](#primery-znacheniy97)

# function transition(transition)

Обновлено 26 марта 2024

[![](/assets/js-api/services/reactions/transition/Code.png)
Code](../../../overview.md)

Функция осуществляет переход в указанное состояние.

Функция может принимать:

* Cтроку, в которой указано состояние для перехода. В формате `/path`.
* Объект `transition`, который в поле `value` содержит путь к нужному стейту и флаг отложенного перехода `deferred`. Флаг принимает значения `true` и `false`.

  Функция с флагом отложенного перехода `deferred=true` эквивалентна тегу [`go`](../../../sa-dsl/tags/reaction-tags.md#тег-go).

  Функция с флагом отложенного перехода `deferred=false` эквивалентна тегу [`go!`](../../../sa-dsl/tags/reaction-tags.md#тег-go).

  Описание объекта отличается от аналогичного в переменной [`$temp`](../../variables/temp.md).



##### Синтаксис

Путь после тега может быть как абсолютным, так и относительным:

* `/` — корневая тема;
* `.` — текущее состояние;
* `..` — состояние на уровень выше;
* `./..` — разделение элементов пути.



##### Примеры значений

```
script: $reactions.transition('/Welcome');
$reactions.transition({ value: '/Welcome', deferred: true });
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней