---
title: function matchPatterns(text, patterns)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/match-patterns
description: function matchPatterns(text, patterns) для смартапов | Функция function
  matchPatterns(text, patterns) для JS API
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function matchPatterns(text, patterns)
---

<!-- Бейджи: Code | Brain -->

# function matchPatterns(text, patterns)

Содержание раздела

* [Примеры значений](#primery-znacheniy89)

# function matchPatterns(text, patterns)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/match-patterns/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/match-patterns/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет сопоставление паттернов для заданного текста. Возвращает объект `NLPResult`: содержит указание какой паттерн сработал и объект `ParseTree`.



##### Примеры значений

Пример вызова:

```
state: Common
  q!: ...
  script:
    var res = $nlp.matchPatterns("test 1", ["test 1", "test 2"]);
    log(res);
```

Пример результата:

```
{
  "patternId": "test 1",
  "pattern": "test 1",
  "effectivePattern": "test 1",
  "score": 0.5,
  "parseTree": {
    "tag": "root",
    "pattern": "root",
    "text": "test 1",
    "words": [
      "test",
      "1"
    ],
    "_Root": "test 1"
  },
  "weight": 1
}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней