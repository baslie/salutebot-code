---
title: function matchExamples(text, examples)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/match-examples
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function matchExamples(text, examples)
---

<!-- Бейджи: Code | Brain -->

# function matchExamples(text, examples)

Содержание раздела

* [Примеры значений](#primery-znacheniy88)

# function matchExamples(text, examples)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/match-examples/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/match-examples/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет сопоставление текста с заданным набором примеров.
Возвращает:

* ближайший пример;
* количество слов во фразе пользователя, для которых найдено соответствие в примерах;
* вес соответствия.



##### Примеры значений

Пример вызова:

```
state: Common
  q!: ...
  script:
    var res = $nlp.matchExamples("раз раз", ["раз", "два", "три"]);
    log(res);
```

Пример результата:

```
{
  example: "раз",
  weight: 0.5,
  aligned: 1
}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней