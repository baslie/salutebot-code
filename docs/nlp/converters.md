---
title: Конвертеры в Code
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/converters
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- Конвертеры
toc:
- title: Объявление
  level: 2
  id: obyavlenie2
- title: Применение
  level: 3
  id: primenenie2
---

<!-- Бейджи: Code | Brain -->

# Конвертеры в Code

Содержание раздела

* [Объявление](#объявление)
* [Применение](#применение)

# Конвертеры в Code

Обновлено 15 декабря 2023

[![](/assets/nlp/converters/Code.png)
Code](../overview.md)[![](/assets/nlp/converters/Brain.png)
Brain](overview.md)

Конвертеры — скрипты, которые используются для интерпретации значений текста в каждом токене.

Конвертеры позволяют преобразовать данные токена, помещаемые в [`$parseTree`](../js-api/variables/parse-tree.md).

## Объявление

Объявление конвертера:

* при объявлении паттерна;

```
patterns:
        $four = четыре || converter = function() {return 4}
```

* в тегах [`init`](../sa-dsl/tags/declarative-tags.md#init);

```
init: function amountConverter(pt) {
    var ret = pt.Number[0].value;
    return ret;
}
```

* в файле `.js`-библиотек, например `converters.js`.

```
function amountConverter(pt) {
    var ret = pt.Number[0].value;
    return ret;
}
```

В функции конвертеров в качестве первого аргумента передается `$parseTree`.

Вы можете использовать внутри конвертера переменную, в которую передается `$parseTree`. Для этого задайте ее имя первым аргументом функции, вторым аргументом передается контекст.

### Применение

Применение конвертеров:

* Формирование значения из текста.

Сценарий:

```
$Digit = $regexp<\d+> || converter = numberConverterDigit
```

`.js`-файл:

```
function numberConverterDigit(parseTree) {
    return parseInt(parseTree.text);
}
```

* Преобразование значения из маппинга.

Сценарий:

```
$Numeral = (один:1|...) || converter = valueToNumberConverter
```

`.js`-файл:

```
function valueToNumberConverter(parseTree) {
    return parseInt(parseTree.value);
}
```

* Формирование значения из вложенных токенов.

Сценарий:

```
$Numeral = (один:1|...)
$Minutes = $Numeral || converter = minutesConverter
```

`.js`-файл:

```
function minutesConverter(parseTree) {
    return parseInt(parseTree.Numeral.value);
}
```

* Формирование значения из справочников.

Сценарий:

```
$City = $entity<Cities> || converter = сityConverter
```

`.js`-файл:

```
function сityConverter(parseTree) {
    var id = parseTree.City[0].value;
    return Cities[id].value;
}
```

Правило `$entity` записывает в `value` только идентификатор сущности. Список ассоциированных значений содержится в справочнике.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней