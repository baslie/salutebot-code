---
title: function conform(text, number)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/conform
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function conform(text, number)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis21
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii20
---

<!-- Бейджи: Code | Brain -->

# function conform(text, number)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Использование в сценарии](#использование-в-сценарии)

# function conform(text, number)

Обновлено 20 декабря 2023

[![](/assets/js-api/services/caila/conform/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/conform/Brain.png)
Brain](../../../nlp/overview.md)

Согласует слова с числительными.



#### Синтаксис

Метод принимает в качестве аргумента текст в виде строки `string` и число для согласования `number`:

```
$caila.conform("text", number)
```

В качестве ответа передается строка с согласованной фразой.



#### Использование в сценарии

Запрос на согласование фразы:

```
    state:
        q!: conform
        script:
            $reactions.answer($caila.conform("хороший день", 2))
```

Ответ: `хороших дня`.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней