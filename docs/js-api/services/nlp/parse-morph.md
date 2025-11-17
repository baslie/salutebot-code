---
title: function parseMorph(word)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/parse-morph
description: function parseMorph(word) для смартапов | Функция function parseMorph(word)
  для JS API
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function parseMorph(word)
---

<!-- Бейджи: Code | Brain -->

# function parseMorph(word)

Содержание раздела

* [Примеры значений](#primery-znacheniy90)

# function parseMorph(word)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/parse-morph/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/parse-morph/Brain.png)
Brain](../../../nlp/overview.md)

Производит морфологический анализ слова.

Морфологический анализ выполняется с помощью [PyMorphy](https://pymorphy2.readthedocs.io/en/latest/user/guide.html#id3) .



##### Примеры значений

Пример вызова:

```
  script:
    $temp.res = $nlp.parseMorph("яблочки");
    log($temp.res);
  a: {{ $temp.res.normalForm }}
```

Результат вызова:

```
log: {"score":0.5,"normalForm":"яблочко","tags":["inan","neut","NOUN","plur","nomn"]}
answer: яблочко
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней