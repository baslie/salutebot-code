---
title: function inferenceWithToken(text, settings, token)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/inference-with-token
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function inferenceWithToken(text, settings, token)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis27
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii27
---

<!-- Бейджи: Code | Brain -->

# function inferenceWithToken(text, settings, token)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function inferenceWithToken(text, settings, token)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/inference-with-token/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/inference-with-token/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет классифкацию текста c дополнительными параметрами. Метод используется для обращения к стороннему обученному классификатору при помощи API-ключа.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки и API-ключ к стороннему обученному классификатору в виде строк `string`, а также дополнительные параметры:

```
$caila.inferenceWithToken({"phrase":{"text":"greetings"}, "nBest": 5, knownSlots: [{"name":"a", "value":"b"}]}, "token"))
```

Здесь:

* `phrase` — фразы для классификации.
* `nBest` — количество возвращаемых гипотез.
* `knownSlots` — известные слоты:
  + `name` — название слота;
  + `value` — значение слота.

[Подробнее о получении API-ключа](../../../nlp/api/overview.md#section/Autentifikaciya)

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
        q!: inferenceWithToken
        script:
            $reactions.answer(JSON.stringify($caila.inferenceWithToken({"phrase":{"text":"greetings"}, "nBest": 5, knownSlots: [{"name":"a", "value":"b"}]}, "token")));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней