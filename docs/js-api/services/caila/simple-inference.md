---
title: function simpleInference(text)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/simple-inference
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function simpleInference(text)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis33
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii32
---

<!-- Бейджи: Code | Brain -->

# function simpleInference(text)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function simpleInference(text)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/simple-inference/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/simple-inference/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет классифкацию текста без дополнительных параметров.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки в виде строки `string`:

```
$caila.simpleInference("hello")
```

В качестве ответа передается JSON с результатом классифкации фразы.

Определим интент `hello` с тренировочными фразами: hello, hi. Результат классификации фразы `hello`:

```
{
    "intent": {
        "id": 12174, // id интента
        "path": "/hello", // путь к интенту
        "slots": []
    },
    "confidence": 1, // степень уверенности
    "slots": [
        // слоты
    ]
}
```





#### Использование в сценарии

```
    state:
        q!: simpleInference
        script:
            $reactions.answer(JSON.stringify($caila.simpleInference("hello")));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней