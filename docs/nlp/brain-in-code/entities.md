---
title: Заполнение сущностей Brain в Code
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/brain-in-code/entities
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Brain
- Code
breadcrumbs:
- SmartApp Brain
- SmartApp Brain
- Заполнение сущностей
toc:
- title: Название пиццы
  level: 2
  id: nazvanie-pitstsy
- title: Размер пиццы
  level: 2
  id: razmer-pitstsy
- title: Количество
  level: 2
  id: kolichestvo
---

<!-- Бейджи: Brain | Code -->

# Заполнение сущностей Brain в Code

Содержание раздела

* [Название пиццы](#название-пиццы)
* [Размер пиццы](#размер-пиццы)
* [Количество](#количество)

# Заполнение сущностей Brain в Code

Обновлено 15 декабря 2023

[![](/assets/nlp/brain-in-code/entities/Brain.png)
Brain](../overview.md)[![](/assets/nlp/brain-in-code/entities/Code.png)
Code](../../overview.md)

Заполните сущности, которые далее мы будем использовать в сценарии `loan.sc`:

* [название пиццы](#название-пиццы);
* [размер пиццы](#размер-пиццы);
* [количество](#количество).

[Подробнее о создании пользовательских сущностей](https://developers.sber.ru/docs/ru/va/chat/voice-interface/command-recognition/entities/entities-types)

Используйте тестовый виджет для тестирования распознавания сущностей и интентов в различных сообщениях.

## Название пиццы

Добавьте сущность определения названия пиццы `PizzaName` со следующими паттернами:

* для "Маргариты": `маргарит*`;
* для "Пепперони": `(пепперон*/пеперон*)`;
* для "Гавайской": `гавайск*`.

В `DATA` для каждого паттерна укажите значение сущности в формате `string`, в данном случае, это название пиццы: Маргарита, Пепперони, Гавайская.

![LoanType](/assets/nlp/brain-in-code/entities/entities-1-68106fc1e96d9d25610fd4af5cc11d1e.png)

## Размер пиццы

Добавьте сущность определения размера пиццы `PizzaSize` со следующими паттернами:

* маленькая: `(маленьк*/поменьш*)`;
* средняя: `средн*`;
* большая: `*больш*`.

В `DATA` для каждого паттерна укажите значение сущности в формате `string`, В данном случае, это размер пиццы: маленькая, средняя, большая.

![LoanSizeType](/assets/nlp/brain-in-code/entities/entities-2-ea5ac36aabce25577d7d538235622097.png)

## Количество

[Активируйте распознавание системной сущности](https://developers.sber.ru/docs/ru/va/chat/voice-interface/command-recognition/entities/entities-types#sistemnye-sushnosti3) `@duckling.number`.

Далее приступайте к [заполнению интентов](intents.md).

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней