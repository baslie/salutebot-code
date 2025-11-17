---
title: Файлы JS-библиотек в Code
source_url: https://developers.sber.ru/docs/ru/va/code/project/js
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- Файлы проекта
- Файлы проекта
- Файлы JS-библиотек
---

<!-- Бейджи: Code -->

# Файлы JS-библиотек в Code

Обновлено 15 декабря 2023

[![](/assets/project/js/Code.png)
Code](../overview.md)

`.js` — файлы JavaScript-библиотек.

Содержат JavaScript-код, который можно использовать в файлах сценариев. Содержат функции, логику обработки запросов, вызовы внешних систем, работу с памятью и пр.

`.js`-файлы подгружаются в начале сценария при помощи тега `require`:

```
require: scripts/functions.js
```

[Подробнее о работе с тегом `require`](../sa-dsl/tags/declarative-tags.md#require)

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней