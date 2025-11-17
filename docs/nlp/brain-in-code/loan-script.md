---
title: Сценарий опроса клиента Brain в Code
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/brain-in-code/loan-script
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Brain
- Code
breadcrumbs:
- SmartApp Brain
- SmartApp Brain
- Сценарий опроса клиента
---

<!-- Бейджи: Brain | Code -->

# Сценарий опроса клиента Brain в Code

Обновлено 15 декабря 2023

[![](/assets/nlp/brain-in-code/loan-script/Brain.png)
Brain](../overview.md)[![](/assets/nlp/brain-in-code/loan-script/Code.png)
Code](../../overview.md)

В данном сценарии мы опрашиваем клиента, который хочет заказать пиццу. Задача смартапа передать полученную информацию от клиента: название пиццы, размер и количество.

В файл `order.sc` добавьте следующий сценарий:

```
theme: /Order
    state: Pizza
        intent!: /OrderPizza
        script:
            $session.PizzaName = $parseTree._PizzaName
            $session.PizzaSize = $parseTree._PizzaSize
            $session.PizzaCount = $parseTree._PizzaCount
        go!: /Order/Result

    state: Result
        a: Название пиццы: {{ $session.PizzaName }}
        a: Размер пиццы: {{ $session.PizzaSize }}
        a: Количество: {{ $session.PizzaCount }}
```

Здесь:

* При намерении пользователя заказать пиццу `/OrderPizza` срабатывает стейт `Pizza`. Если слоты сущностей для интента не заполнены, то мы дозапрашиваем информацию при помощи процесса слот-филлинга. Полученные данные записываем в `$session` для финального вывода полученной информации от клиента.

```
    state: Pizza
        intent!: /OrderPizza
        script:
            $session.PizzaName = $parseTree._PizzaName
            $session.PizzaSize = $parseTree._PizzaSize
            $session.PizzaCount = $parseTree._PizzaCount
        go!: /Order/Result
```

* Выводим всю полученную смартапом информацию.

```
    state: Result
        a: Название пиццы: {{ $session.PizzaName }}
        a: Размер пиццы: {{ $session.PizzaSize }}
        a: Количество: {{ $session.PizzaCount }}
```

[Протестируйте работу смартапа при помощи тестового виджета](test.md).

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней