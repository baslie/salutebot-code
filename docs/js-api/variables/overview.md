---
title: Переменные JavaScript в Code
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/variables/overview
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- Передача переменных
---

<!-- Бейджи: Code -->

# Переменные JavaScript в Code

Обновлено 10 апреля 2024

[![](/assets/js-api/variables/overview/Code.png)
Code](../../overview.md)

При вызове скриптовых расширений, задаваемых в тегах `if:`, `else:`, `elseif:`, `script:` и макроподстановках в ответах `{{}}` (тег `a:`), передаются следующие переменные:

* [`$context`](context.md);
* [`$parseTree`](parse-tree.md);
* [`$client`](client.md);
* [`$session`](session.md);
* [`$request`](request.md);
* [`$response`](response.md);
* [`$temp`](temp.md);
* [`$injector`](injector.md).

Скрипт может быть задан:

* Непосредственно в стейте.

```
    state: Hello
        q!: * меня зовут $Name *
        script:
            $session.name = $Name
        a: Привет, {{$session.name}}!
```

* Вызовом функции. В таком случае объявляем скрипт в JS-файле и вызываем его в стейте после тега `script`.

Например, объявляем скрипт в JS-файле:

```
function getName() {
    var $session = $jsapi.context().session;
    $session.name = $Name;
}
```

Вызываем скрипт в стейте:

```
    state: Hello
        q!: * меня зовут $Name *
        script: getName()
        a: Привет, {{$session.name}}!
```

Следует отметить, что в JS-файлах ко всем переменным можно обратиться, убрав знак `$` и добавив в начало `$jsapi.context()`.

Например, в JS-файле `$session`, будет иметь вид: `$jsapi.context().session`.

Объявление переменных: `var $session = $jsapi.context().session`.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней