---
title: function markupWithToken(text, token)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/markup-with-token
description: function markupWithToken(text, token) для смартапов | Функция function
  markupWithToken(text, token) для JS API
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function markupWithToken(text, token)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis31
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii31
---

<!-- Бейджи: Code | Brain -->

# function markupWithToken(text, token)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function markupWithToken(text, token)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/markup-with-token/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/markup-with-token/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет разметку переданного текста. Метод используется для обращения к стороннему обученному классификатору при помощи API-ключа.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки и API-ключ к стороннему обученному классификатору в виде строк `string`:

```
$caila.markup("markup text", "token")
```

[Подробнее о получении API-ключа](../../../nlp/api/overview.md#section/Autentifikaciya)

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
        q!: markup text with token
        script:
            $reactions.answer(JSON.stringify($caila.markupWithToken("greetings", "API token")));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней