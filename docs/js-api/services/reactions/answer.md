---
title: function answer(text)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/reactions/answer
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
- Chat App
breadcrumbs:
- function answer(text)
toc:
- title: Форматирование текста
  level: 2
  id: formatirovanie-teksta3
- title: Выбор случайного ответа
  level: 2
  id: vybor-sluchaynogo-otveta2
- title: Примеры
  level: 2
  id: primery7
- title: Поддерживаемые Markdown-теги
  level: 3
  id: podderzhivaemye-markdown-tegi2
- title: Использование переменной в ответе
  level: 3
  id: ispolzovanie-peremennoy-v-otvete2
- title: Случайный ответ с помощью YAML-справочника
  level: 3
  id: sluchaynyy-otvet-s-pomoshyu-yaml-spravochnika2
---

<!-- Бейджи: Code | Chat App -->

# function answer(text)

Содержание раздела

* [Форматирование текста](#форматирование-текста)
* [Поддерживаемые Markdown-теги](#поддерживаемые-markdown-теги)
* [Выбор случайного ответа](#выбор-случайного-ответа)
* [Примеры](#примеры)
* [Использование переменной в ответе](#использование-переменной-в-ответе)
* [Случайный ответ с помощью YAML-справочника](#случайный-ответ-с-помощью-yaml-справочника)

Развернуть

# function answer(text)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/reactions/answer/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/reactions/answer/ChatApp.png)
Chat App](https://developers.sber.ru/docs/ru/va/chat/title-page)

Функция выводит простой текстовый ответ.

Имеет один параметр `text` — текстовый ответ.

В тексте ответа можно использовать подстановки и функции. Внутри скобок `{{ }}` может находиться любое валидное JavaScript-выражение или те же переменные и функции, что и в скриптах.

## Форматирование текста

Ответ бота можно отформатировать с помощью Markdown-разметки. Для этого в качестве параметра `$reactions.answer()` нужно передать объект вида:

```
{
    "value": "Хочу отметить, что вам крупно повезло! Сегодня действует http://example.com!",
    // поле markdown содержит ответ, отформатированный с помощью Markdown-разметки
    "markdown": "**Хочу отметить**, что вам крупно повезло! Сегодня действует [акция](http://example.com)!"
}
```

Пример:

```
script:
    $reactions.answer({
        "value": "Хочу отметить, что вам крупно повезло! Сегодня действует http://example.com!",
        "markdown": "**Хочу отметить**, что вам крупно повезло! Сегодня действует [акция](http://example.com)!"
    });
```

### Поддерживаемые Markdown-теги

Доступны следующие элементы форматирования:

| Форматирование | Пример кода |
| --- | --- |
| Жирный шрифт | ``` Жирный шрифт ``` |
| Курсив | ``` Курсив ``` или ``` Курсив ``` |
| Зачеркнутый шрифт | ``` Зачеркнутый шрифт ``` |
| Ссылка | ``` текст ссылки ``` |
| Маркированный список | ``` * Пункт 1 * Пункт 2 * Пункт 3 ``` или ``` * Пункт 1 * Пункт 2 * Пункт 3 ``` |

## Выбор случайного ответа

Для выбора случайного ответа используйте функцию `selectRandomArg`, а варианты ответов перечисляйте через запятую:

```
script: $reactions.answer(selectRandomArg('Привет', 'Здарова'));
```

В качестве аргумента функции вы так же можете передать YAML-справочник с вариантами ответов.

## Примеры

### Использование переменной в ответе

```
script: $reactions.answer('Привет {{ $client.name }}!');
```

### Случайный ответ с помощью YAML-справочника

Пример справочника:

```
RandomReplies:
    - 'Фраза 1'
    - 'Фраза 2'
    - 'Фраза 3'
    - 'Фраза 4'
    - 'Фраза 5'
```

Вывод случайного ответа:

```
require: answers.yaml
    var = answers
    state: random
        q!: случайная фраза
        script: $reactions.answer(selectRandomArg($global.answers["RandomReplies"]));
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней