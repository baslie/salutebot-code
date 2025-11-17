---
title: function inflect(text, declension)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/inflect
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function inflect(text, declension)
---

<!-- Бейджи: Code | Brain -->

# function inflect(text, declension)

Содержание раздела

* [Примеры значений](#primery-znacheniy86)

# function inflect(text, declension)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/inflect/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/inflect/Brain.png)
Brain](../../../nlp/overview.md)

Склоняет слово в требуемый формат.

Склонение выполняется с помощью [библиотеки PyMorphy](https://pymorphy2.readthedocs.io/en/latest/user/grammemes.html) . Склонения `declension` задаются в ее формате.



##### Примеры значений

В примере: `gent` — родительный падеж.

```
a: И склонен в нужную форму: Вы из {{ capitalize($nlp.inflect("питер", "gent")) }}?
```

В примере: `loct` — предложный падеж.

```
state:
        q!: inflect
        a: {{ $nlp.inflect('Москва', "loct") }}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней