---
title: function simpleInferenceWithToken(text, token)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/simple-inference-with-token
description: function simpleInferenceWithToken(text, token) для смартапов | Функция
  function simpleInferenceWithToken(text, token) для JS API
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function simpleInferenceWithToken(text, token)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis34
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii33
---

<!-- Бейджи: Code | Brain -->

# function simpleInferenceWithToken(text, token)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function simpleInferenceWithToken(text, token)

Обновлено 18 июля 2024

[![](/assets/js-api/services/caila/simple-inference-with-token/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/simple-inference-with-token/Brain.png)
Brain](../../../nlp/overview.md)

Выполняет классификацию текста без дополнительных параметров. Метод используется для обращения к стороннему обученному классификатору при помощи API-ключа.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки и API-ключ к стороннему обученному классификатору в виде строк `string`:

```
$caila.simpleInferenceWithToken("text", "token")
```

[Подробнее о получении API-ключа](../../../nlp/api/overview.md#section/Autentifikaciya)

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
        q!: simpleInferenceWithToken
        script:
            $reactions.answer(JSON.stringify($caila.simpleInferenceWithToken("hello", "token")));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней