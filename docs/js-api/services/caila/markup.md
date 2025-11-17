---
title: function markup(text)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/markup
description: function markup(text) для смартапов | Функция function markup(text) для
  JS API
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function markup(text)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis30
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii30
---

<!-- Бейджи: Code | Brain -->

# function markup(text)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function markup(text)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/markup/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/markup/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет разметку переданного текста.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки в виде строки `string`:

```
$caila.markup("markup text")
```

В качестве ответа передается размеченная фраза в формате JSON. Результат разметки фразы `markup text`:

```
{
    "source": "markup text", //фраза для разметки
    "words": [
        {
            "annotations": {
                "lemma": "markup",
                "pos": "X" //часть речи
            },
            "startPos": 0, //позиция слова во фразе
            "endPos": 6,
            "pattern": false,
            "punctuation": false,
            "source": "markup",
            "word": "markup" //нормализованная форма слова
        },
        {
            "annotations": {
                "lemma": "text",
                "pos": "X" //часть речи
            },
            "startPos": 7, //позиция слова во фразе
            "endPos": 11,
            "pattern": false,
            "punctuation": false,
            "source": "text",
            "word": "text" //нормализованная форма слова
        }
    ]
}
```





#### Использование в сценарии

```
    state:
        q!: markup text
        script:
            $reactions.answer(JSON.stringify($caila.markup("markup text")));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней