---
title: function conform(word, number)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/conform
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function conform(word, number)
---

<!-- Бейджи: Code | Brain -->

# function conform(word, number)

Содержание раздела

* [Примеры значений](#primery-znacheniy84)

# function conform(word, number)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/conform/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/conform/Brain.png)
Brain](../../../nlp/overview.md)

Согласование слова с числительным.

Согласование выполняется с помощью [библиотеки PyMorphy](https://pymorphy2.readthedocs.io/en/latest/user/guide.html#id8) .



##### Примеры значений

```
# будет выведено 5 яблок
a: Русский текст может быть согласован с числительным: 5 {{ $nlp.conform("яблоко", 5) }}
```

```
script:
         $session.points = $nlp.conform("правильный", $session.myPoints) + " " + $nlp.conform("ответ", $session.myPoints);
a: У тебя {{$session.myPoints}} {{$session.points}}.
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней