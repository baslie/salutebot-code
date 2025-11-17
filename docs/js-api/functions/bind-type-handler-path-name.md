---
title: function bind(type, handler, path, name)
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/functions/bind-type-handler-path-name
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- function bind(type, handler, path, name)
toc:
- title: Параметры
  level: 4
  id: parametry10
- title: Подробнее об обработчикахonScriptErrorиonAnyError
  level: 4
  id: podrobnee-ob-obrabotchikah-on-script-error-i-on-any-error2
- title: Подробнее об обработчикеpreMatch
  level: 4
  id: podrobnee-ob-obrabotchike-pre-match2
- title: Примеры значений
  level: 4
  id: primery-znacheniy54
---

<!-- Бейджи: Code -->

# function bind(type, handler, path, name)

Содержание раздела

* [Параметры](#параметры)
* [Подробнее об обработчиках onScriptError и onAnyError](#подробнее-об-обработчикахonscripterrorиonanyerror)
* [Подробнее об обработчике preMatch](#подробнее-об-обработчикеprematch)
* [Примеры значений](#примеры-значений)

# function bind(type, handler, path, name)

Обновлено 28 декабря 2023

[![](/assets/js-api/functions/bind-type-handler-path-name/Code.png)
Code](../../overview.md)

Функция предназначена для [установки обработчиков](../pre-post-process.md) `preProcess` и `postProcess`.

Обработчики работают только если функция объявлена внутри тега [`init:`](../../sa-dsl/tags/declarative-tags.md#init).

#### Параметры

* `type` — тип обработчика.
* `handler` — callback-функция с сигнатурой `function($context)` будет вызвана в соответствующий момент обработки запроса клиента.
* `path` — путь, к которому нужно привязать обработчик, по умолчанию `/`.
* `name` — короткое имя обработчика, его идентификатор.

Типы обработчиков `type`:

* `preMatch` — вызывается перед классификатором интентов (матчером). `preMatch` может принудительно отменить выполнение матчера, если выставить переменную `$temp.targetState = ".."`.
* `preProcess` — вызывается после классификатора, но перед началом выполнения реакций `targetState`.
* `postProcess` — вызывается после завершения обработки запроса.
* `onScriptError` — вызывается, если выполнение сценария прервано по ошибке выполнения JS-кода. После обработчика `onScriptError` может быть выполнен `postProcess`.
* `onAnyError` — вызывается, если выполнение сценария прервано по какой-либо ошибке, в том числе внутренней ошибке сервера. Вызов происходит не при каждом типе ошибок.

После обработчика `onAnyError` не выполняется `postProcess`.

#### Подробнее об обработчиках `onScriptError` и `onAnyError`

* `onScriptError`

Вызывается, если ошибка возникла в ходе выполнения JS-кода. В коде отлавливаются ошибки, из которых берется сообщение и дублируется в `onScriptError`. По возможности указывается место, где в JS-коде возникла ошибка.

Рассмотрим сценарий:

```
theme: /

    state: error test
        q!: error test
        script:
            someError(); # вызовет ошибку, так как мы не определяли функцию someError()
```

Здесь будет вызвана ошибка типа `ReferenceError` с сообщением `““someError” is not defined”`, так как не была определена функция `someError()`. Эта ошибка отлавливается при помощи `onScriptError`.

* `onAnyError`

Вызывается в нескольких случаях:

1. Возникла ошибка, повлекшая `onScriptError`. Но в сценарии смартапа нет обработчика ошибок, который отлавливает случаи `onScriptError`.
2. Возникла любая другая ошибка в процессе обработки запроса.

Рассмотрим тип ошибок `DialogException`. Такая ошибка возникает в нескольких случаях:

* Для отправленного запроса не был определен `state`. Сообщение об ошибке: `"No target state was determined for query"`.
* Если смартап попадает в бесконечный цикл. Например, в `postProcess` обработке перенаправляем смартап на стейт, а потом снова в тот же `postProcess`. Сообщение об ошибке: `"Infinite loop was detected for state <statename> in postProcess transition"`.
* Если осуществляется переход `transition` в несуществующий стейт. Сообщение об ошибке: `"State not found for path <statename>"`.

#### Подробнее об обработчике `preMatch`

В `preMatch` есть возможность изменить `$request.query`.

Для успешного изменения `$request.query` в файле `chatbot.yaml` должно быть прописано в блоке `nlp`: `modifyRequestInPreMatch: true`.

Пример сценария:

```
entryPoint: main.sc

nlp:
    modifyRequestInPreMatch: true
```

```
init:
    var f = function(ctx) {
        ctx.request.query = "новый текст";
    }
    $jsapi.bind({
        type:"preMatch",
        handler:f,
        path:"/",
        name:"modify query"
    })

theme: /
    state:
        q!: *
        a: {{ $parseTree.text }}
```

#### Примеры значений

* Использование `onAnyError` при динамическом формировании сообщения об ошибке.

Например, выдача случайного сообщения из 3 возможных:

```
init: bind('onAnyError', function ($context) {
    var r = $jsapi.random(3);
    if (r == 0) {
        $reactions.answer('Что-то пошло не так');
    } else if (r == 1) {
        $reactions.answer('Все сломалось, нам очень жаль');
    } else {
        $reactions.answer('Произошла ошибка');
    }
});
```

Формирование сообщения об ошибке:

```
init:
    bind("onAnyError", function($context) {
        if ($context.injector.testMode
            && $context.exception.message
            && $context.exception.message === 'No target state was determined for query') {
            $reactions.answer("Для вопроса " + $context.request.query + " не найден стейт!");
        }
    });

theme:
    state: Without CatchAll
        q: Useless
        a: Useless
```

* `onScriptError` используется для обработки исключений, возникших во время выполнения скрипта: из-за ошибки или выброшенных специально.

Рассмотрим пример в связке с http-запросами: в сценарии обрабатываем случай успешного выполнения запроса, для ошибочного создаем отдельный обработчик в `onScriptError`.

```
function callApi() {
    var result = $http.get('https://example.com');
    if (!result.isOk) {
        throw {httpStatus: result.status};
    }
    return result.data;
}

...

state: ExternalApi
    script:
        var apiResult = callApi();
        $reactions.answer("Result " + formatApiResult(apiResult));

...

init:
    bind("onScriptError", function($context) {
        if ($context.exception.httpStatus) {
            $reactions.answer("Ошибка вызова внешнего сервиса. Код ошибки: " + $context.exception.httpStatus);
        }
    });
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней