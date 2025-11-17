---
title: function tokenize(text)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/tokenize
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function tokenize(text)
toc:
- title: Примеры значений
  level: 2
  id: primery-znacheniy91
---

<!-- Бейджи: Code | Brain -->

# function tokenize(text)

Содержание раздела

* [Примеры значений](#примеры-значений)

# function tokenize(text)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/tokenize/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/tokenize/Brain.png)
Brain](../../../nlp/overview.md)

Разбивает текст на слова (токены). Возвращает массив строк.

Поддерживаемые типы токенизаторов:

* regexp — простой токенизатор на регулярных выражениях.
* srx — конфигурируемый токенизатор на базе настраиваемых правил сегментации. При указании данного токенизатора требуется указать файл грамматики в параметре `srxPath`.
* default — способ сегментации по умолчанию. Является предпочтительной опцией при совместном использовании паттернов и классификатора.

Тип токенизатора и его параметры указываются в файле `chatbot.yaml`:

```
nlp:
    tokenizer: default
    morphology: pyMorphy
    costStrategy: weighted
    contextHistoryDepth: 1
    nbest: 1
    vocabulary: sys/dictionaries/opencorpora/opcorpora-vocab.json
    synonyms: sys/dictionaries/opencorpora/weighted-synonyms-pmiIdf.json
```

## Примеры значений

```
 state: TestTokenize
        q!: tokenize
        script:
            $temp.m = $nlp.tokenize("Добрый день, помогите с заказом. Спасибо. С наступающим.");
        a: morph: {{$temp.m[0]}}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней