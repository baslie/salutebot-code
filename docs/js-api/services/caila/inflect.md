---
title: function inflect(text, tag declension)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/caila/inflect
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- function inflect(text, tag declension)
toc:
- title: Синтаксис
  level: 4
  id: sintaksis28
- title: Использование в сценарии
  level: 4
  id: ispolzovanie-v-stsenarii28
---

<!-- Бейджи: Code | Brain -->

# function inflect(text, tag declension)

Содержание раздела

* [Синтаксис](#синтаксис)
* [Падеж](#padezh2)
* [Использование в сценарии](#использование-в-сценарии)

# function inflect(text, tag declension)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/caila/inflect/Code.png)
Code](../../../overview.md)[![](/assets/js-api/services/caila/inflect/Brain.png)
Brain](../../../nlp/overview.md)

Склоняет текст в требуемый формат.



#### Синтаксис

Метод принимает в качестве аргумента текст для разметки в виде строки `string` и тег склонения `tag`:

```
$caila.inflect("text", ["tag"])
```

В качестве ответа передается строка с фразой в требуемом падеже.



##### Падеж

| `tag` | Значение | Пояснение | Примеры |
| --- | --- | --- | --- |
| `nomn` | именительный | Кто? Что? | **хомяк** ест |
| `gent` | родительный | Кого? Чего? | у нас нет **хомяка** |
| `datv` | дательный | Кому? Чему? | сказать **хомяку** спасибо |
| `accs` | винительный | Кого? Что? | хомяк читает **книгу** |
| `ablt` | творительный | Кем? Чем? | зерно съедено **хомяком** |
| `loct` | предложный | Кем? Чем? | зерно съедено **хомяком** |
| `voct` | звательный | Его формы используются при обращении к человеку. | Саш, пойдем в кино. |
| `gen2` | второй родительный (частичный) | | ложка сахару (`gent` - производство сахара); стакан яду (`gent` - нет яда) |
| `acc2` | второй винительный | | записался в солдаты |
| `loc2` | второй предложный (местный) | | я у него в долгу (`loct` - напоминать о долге); висит в шкафу (`loct` - монолог о шкафе); весь в снегу (`loct` - писать о снеге) |






#### Использование в сценарии

```
    state:
        q!: inflect
        script:
            $reactions.answer($caila.inflect("Мария дала книгу", ["voct"]))
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней