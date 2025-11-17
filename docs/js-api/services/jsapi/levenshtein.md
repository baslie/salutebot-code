---
title: $jsapi.levenshtein.distance
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/jsapi/levenshtein
description: $jsapi.levenshtein.distance | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- jsapi.levenshtein.distance
---

<!-- Бейджи: Code -->

# $jsapi.levenshtein.distance

Обновлено 3 сентября 2024

[![](/assets/js-api/services/jsapi/levenshtein/Code.png)
Code](../../../overview.md)

Расстояние Левенштейна — метрика, отражающая различия между двумя строковыми последовательностями. Например, для двух одинаковых последовательностей расстояние равно нулю. Чем больше различий в строках, тем больше расстояние Левенштейна.

С помощью этой метрики можно определить минимальное количество односимвольных преобразований (удаления, вставки или замены), которые нужны для превращения одной последовательности в другую.

Функция `$jsapi.levenshtein.distance` позволяет рассчитать расстояние Левенштейна в массиве при использовании в скрипте сценария.

**Входные параметры функции**

`string1` и `string2` — две строки, которые необходимо сравнить.

**Результат функции**

Ответ типа `int` с расстоянием между `string1` и `string2`.

**Пример использования**

```
script:
    var o = $jsapi.levenshtein.distance("lewenstein", "levenshtein")
    log(o);

/// в результате вернет 2
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней