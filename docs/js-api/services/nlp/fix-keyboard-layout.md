---
title: function fixKeyboardLayout(text)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/nlp/fix-keyboard-layout
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function fixKeyboardLayout(text)
---

<!-- Бейджи: Code | Brain -->

# function fixKeyboardLayout(text)

Содержание раздела

* [Параметры](#parametry18)
* [Примеры значений](#primery-znacheniy85)

# function fixKeyboardLayout(text)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/nlp/fix-keyboard-layout/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/nlp/fix-keyboard-layout/Brain.png)
Brain](../../../nlp/overview.md)

Метод исправляет текст, изменяя раскладку из латиницы в кириллицу.
Принимает строку, возвращает отформатированную строку.

Например, для строки `ghbdtn` вернет `привет`.





##### Параметры

Если в тексте есть знаки кириллицы, возвращает `null`.
К цифрам форматирование не применяется.

Если вызвать функцию, ничего ей не передав, смартап упадет с ошибкой.

Если передать объект вместо строки, то функция вернет `хщиоусе Щиоусеъ`, т.к. изменит раскладку строки `[object Object]`.





##### Примеры значений

```
 state:
        q!: *
        a: {{ $nlp.fixKeyboardLayout($parseTree.text) }}
```

Использование в комбинации с `$nlp.match`:

```
state: Hello
        q!: (привет/здарова/доброе утро)
        a: И тебе {{ $parseTree.text }}!

    state: CatchAll
        q!: *
        script:
            var text = $parseTree.text;
            $temp.fixedText = $nlp.fixKeyboardLayout(text);
        if: $temp.fixedText
            script:
                var matchResults = $nlp.match($temp.fixedText, "/");
                $parseTree = matchResults.parseTree;
                $temp.nextState = matchResults.targetState;
            go!: {{ $temp.nextState }}

        else:
            a: Что-то я ничего не понял...
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней