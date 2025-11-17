---
title: function inference(text, settings)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/inference
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function inference(text, settings)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis26
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii26
---

<!-- Бейджи: Code | Brain -->

# function inference(text, settings)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function inference(text, settings)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/inference/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/inference/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет классифкацию текста c дополнительными параметрами.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки в виде строки `string` и дополнительные параметры:

```
$caila.inference({"phrase":{"text":"greetings"}, "nBest": 5, knownSlots: [{"name":"a", "value":"b"}]})
```

Здесь:

* `phrase` — фразы для классификации.
* `nBest` — количество возвращаемых гипотез.
* `knownSlots` — известные слоты:
  + `name` — название слота;
  + `value` — значение слота.

В качестве ответа передается JSON с результатом классифкации фразы.

Определим интент `hello` с тренировычными фразами: hello, hi. Результат классификации фразы `hello`:

```
{
    "phrase": {
        "text": "hello",
        "entities": []
    },
    "variants": [
        {
            "intent": {
                "id": 12174, // id интента
                "path": "/hello", // путь к интенту
                "slots": [
                    // слоты
                ]
            },
            "confidence": 1, // степень уверенности
            "slots": []
        }
    ]
}
```





#### Использование в сценарии

```
    state:
        q!: inference
        script:
            $reactions.answer(JSON.stringify($caila.inference({"phrase":{"text":"hello"}, "nBest": 5, knownSlots: [{"name":"a", "value":"b"}]})));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней