---
title: function resolvePath(basePath, relativePath)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/jsapi/resolve-path
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function resolvePath(basePath, relativePath)
---

<!-- Бейджи: Code -->

# function resolvePath(basePath, relativePath)

Содержание раздела

* [Примеры значений](#primery-znacheniy73)

# function resolvePath(basePath, relativePath)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/jsapi/resolve-path/Code.png)
Code](../../../overview.md)

Метод предназначен для приведения относительных путей состояний к абсолютным.



##### Примеры значений

```
\$jsapi.resolvePath($context.currentState, `..`) - на уровень выше
\$jsapi.resolvePath('/state1', `./state2/state3`) == `/state1/state2/state3/`
\$jsapi.resolvePath('/state1', `/root`) == `/root`
\$jsapi.resolvePath('/state1', `state2`) == `/state1/state2`
\$jsapi.resolvePath('/state1', `./unused/..`) == `/state1`
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней