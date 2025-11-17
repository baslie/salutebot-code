---
title: $fetch.all(iterable)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/fetch/all
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- fetch
- fetch
- $fetch.all(iterable)
toc:
- title: Пример
  level: 2
  id: primer110
---

<!-- Бейджи: Code -->

# $fetch.all(iterable)

Содержание раздела

* [Пример](#пример)

# $fetch.all(iterable)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/fetch/all/Code.png)
Code](../../../overview.md)

Возвращает промис, который выполнится тогда, когда будут выполнены все промисы, переданные в виде перечисляемого аргумента, или отклонен любой из переданных промисов.

В параметр передается перечисляемый объект, например массив.

## Пример

```
var first = $fetch.post('http://example1.ru')
 .then(function(response) {
    if (response.status != 200) {
         throw "example1 failed: " + response.status;
    }
  $jsapi.log('first then');
  return response.json();
 });

var second = $fetch.post('http://example2.ru')
 .then(function(response) {
    if (response.status != 200) {
         throw "example2 failed: " + response.status;
    }
  $jsapi.log('second then');
  return response.json();
 });

$fetch.all([first, second])
 .then(function(jsons) {
    $jsapi.log("success");
})
 .catch(function (error) {
  $jsapi.log(error);
})

$jsapi.log('scenario');
```

Последовательность вывода в консоль при выполнении кода:

```
scenario
second then
first then
success
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней