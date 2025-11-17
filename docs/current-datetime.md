---
title: Текущие дата и время в Code
source_url: https://developers.sber.ru/docs/ru/va/code/current-datetime
reading_time: 1
badges:
- Code
breadcrumbs:
- Текущие дата и время
toc:
- title: Параметры
  level: 2
  id: parametry9
- title: Ответ сервиса
  level: 2
  id: otvet-servisa2
---

<!-- Бейджи: Code -->

# Текущие дата и время в Code

Содержание раздела

* [Параметры](#параметры)
* [Ответ сервиса](#ответ-сервиса)

# Текущие дата и время в Code

Обновлено 15 декабря 2023

[![](/assets/current-datetime/Code.png)
Code](overview.md)

Этот сервис просто возвращает текущие дату и время в указанном часовом поясе.

`https://smartapp-code.sberdevices.ru/tools/api/now?tz=Europe/Moscow&format=dd/MM/yyyy`

## Параметры

В качестве параметров запроса можно указать:

* `tz` — код часового пояса (список кодов можно увидеть [здесь](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) );
* `format` — в каком формате нужно вернуть дату-время ([синтаксис](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/text/SimpleDateFormat.html) форматов).

По умолчанию сервис вернет текущие дату и время в часовом поясе UTC в формате `dd/MM/yyyy HH:mm`.

## Ответ сервиса

В ответе сервис возвращает JSON такого вида

```
{
    "timezone": "Etc/UTC",
    "formatted": "16.08.2018 13:45",
    "timestamp": 1534427103257,
    "weekDay": 4,
    "day": 16,
    "month": 8,
    "year": 2018,
    "hour": 13,
    "minute": 45
}
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней