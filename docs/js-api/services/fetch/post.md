---
title: $fetch.post(url, settings)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/fetch/post
reading_time: 1
badges:
- Code
breadcrumbs:
- fetch
- fetch
- $fetch.post(url, settings)
toc:
- title: Пример
  level: 2
  id: primer19
---

<!-- Бейджи: Code -->

# $fetch.post(url, settings)

Содержание раздела

* [Пример](#пример)

# $fetch.post(url, settings)

Обновлено 15 декабря 2023

[![](/assets/js-api/services/fetch/post/Code.png)
Code](../../../overview.md)

Передает данные на внешний сервер.

Эквивалентен вызову `$fetch.query(url, settings)`, при условии, что `settings.method == 'POST'`.

Параметры метода:

* `url` — адрес внешнего бэкенда.
* `settings` — валидный JSON с данными для обработки в бэкенде.

## Пример

```
state: UsingNewFetchMethod
    script:
        function successHandlerParseResponseJson(response) {
            log("Выполнение функции successHandlerParseResponseJson() завершено");
            const state = response.json().content.array[0].state;   // Обработка полученного ответа
            $temp.answerToUserString = "Ответ пользователю на основе результатов запроса к внешнему бэкенду: " + state;
        }

        function errorHandler(error) {
            log("Выполнение функции errorHandler() завершено");
            return "Все сломалось. Ошибка выполнения запроса. Вот ошибка: " + error;
        }

        //Адрес внешнего бэкенда
        var url = "http://mockserver/another/back";

        //Данные для обработки в бэкенде
        var options = {
            dataType: 'json',
            headers: {
                'Content-Type': 'application/json',
            },
            body: {},
        };

        //Вызов метода
        $fetch.post(url, options)
            .then(successHandlerParseResponseJson)
            .catch(errorHandler);

        log("Выполнение всего скрипта завершено");

    a: {{$temp.answerToUserString}}
```

Несколько последовательных запросов к внешнему серверу можно сделать с помощью последовательного вызова методов `then()` и `catch()`.

В этом случае скрипт выполнится до конца, после чего будут выполнены зарегистрированные колбэки. Сценарий перейдет к следующему шагу после выполнения всех отложенных функций.

Последовательность вывода в консоль при выполнении кода:

```
//При успешном запросе

Выполнение всего скрипта завершено

Выполнение функции successHandlerParseResponseJson() завершено

//При ошибке

Выполнение всего скрипта завершено

Выполнение функции errorHandler() завершено
```

Полученные ответы можно обрабатывать как с помощью тэга `a`, так и с помощью метода [`$reactions.answer()`](../reactions/answer.md)

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней