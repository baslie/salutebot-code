---
title: function match(text, state)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/match
description: function match(text, state) для смартапов | Функция function match(text,
  state) для JS API
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function match(text, state)
---

<!-- Бейджи: Code | Brain -->

# function match(text, state)

Содержание раздела

* [Примеры значений](#primery-znacheniy87)

# function match(text, state)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/match/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/match/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет сопоставление паттернов для заданного текста. Возвращает объект `NLPResult`: содержит указание какой паттерн в каком состоянии сработал и объект `parseTree`.



##### Примеры значений

Пример вызова:

```
state: A
  q!: ...
  script:
    var res = $nlp.match("test 1", "/");
    log(res);
    $reactions.transition(res.targetState);
```

Пример результата:

```
{
  "targetState": "/1",
  "patternId": "main.sc:12",
  "pattern": "* test 1 *",
  "effectivePattern": "* test 1 *",
  "score": 1,
  "parseTree": {
    "tag": "root",
    "pattern": "root",
    "text": "test 1",
    "words": [
      "test",
      "1"
    ]
  }
}
```

Параметр `onlyThisState` в `$nlp.match()` не поддерживается. Если есть необходимость использовать флаг `onlyThisState = true`, используйте модификатор `modal = true` в стейте.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней