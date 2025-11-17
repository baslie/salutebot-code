---
title: function checkMyVocabulary(word)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/check-my-vocabulary
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function checkMyVocabulary(word)
---

<!-- Бейджи: Code | Brain -->

# function checkMyVocabulary(word)

Содержание раздела

* [Примеры значений](#primery-znacheniy83)

# function checkMyVocabulary(word)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/check-my-vocabulary/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/check-my-vocabulary/Brain.png)
Brain](../../../nlp/overview.md)

Проверяет, является ли переданный текст словарным словом.

Для проверки используется словарь, указанный в `chatbot.yaml` в параметре `nlp.vocabulary`. Словарь может быть создан в лингвистическом сервисе действием `vocabulary-from-text`.

Возвращает:

* `false` — если слово не находится в словаре;
* `true` — если слово является словарным.



##### Примеры значений

```
state:
    q!: *
    script:
        var text = $parseTree.text;
        $temp.res = $nlp.checkMyVocabulary(text);
    if: $temp.res
        a: есть в словаре
    else:
        a: нет в словаре
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней