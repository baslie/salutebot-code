---
title: function random(arg)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/reactions/random
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function random(arg)
---

<!-- Бейджи: Code -->

# function random(arg)

Содержание раздела

* [Примеры значений](#primery-znacheniy96)

# function random(arg)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/reactions/random/Code.png)
Code](../../../overview.md)

Генератор случайных чисел. Метод возвращает целочисленные значения от `0` до `max` (не включая `maх`).

Особые свойства функции:

* Возвращаемые значения могут быть переопределены в тестах.
* Возвращаемые значения могут быть переопределены в структуре `$request.data.smartRandom`.
* Все сгенерированные значения записываются в `$response` и могут быть использованы для повторного выполнения сценария с такими же результатами.
* Метод проверяет сгенерированные значения,чтобы случайные значения не повторялись чаще, чем в 1/2 от количества вариантов.



##### Примеры значений

```
 state:
        q!: *
        script:
            // проверим, что значения не повторяются
            var check = []
            for (var i = 0; i < 5; i++) {
                var r = $reactions.random(10, $context);
                if (check.indexOf(r) != -1) {
                    throw "значения повторяются";
                }
                check.push(r);
            }
            $reactions.answer("Проверка выполнена", $context);
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней