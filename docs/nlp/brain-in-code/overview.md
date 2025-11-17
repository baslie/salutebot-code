---
title: Пример использования SmartApp Brain
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/brain-in-code/overview
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Brain
- Code
---

<!-- Бейджи: Brain | Code -->

# Пример использования SmartApp Brain

Обновлено 15 декабря 2023

[![](/assets/nlp/brain-in-code/overview/Brain.png)
Brain](../overview.md)[![](/assets/nlp/brain-in-code/overview/Code.png)
Code](../../overview.md)

В этом разделе на примере смартапа для заказа пиццы демонстрируется использование SmartApp Brain в среде разработки [Code](../../overview.md).

Этот смартап умеет:

* принимать заказ и передавать его для дальнейшей обработки;
* узнавать название пиццы, ее размер и количество

Для корректной работы смартапа вам потребуются:

* [интенты](../../sa-dsl/tags/intents-tags.md);
* [системные и пользовательские сущности](../entities/overview.md);
* [модуль слот-филлинга](../slot-filling/overview.md).

Чтобы создать смартап на основе SmartApp Brain нужно выполнить следующие шаги:

1. [Создание проекта Code](https://developers.sber.ru/docs/ru/va/chat/script/project-creation#sozdanie-proekta-code).
2. [Подготовка проекта Code](project.md).
3. [Основной сценарий смартапа](input-script.md).
4. [Сценарий опроса пользователя](loan-script.md).
5. [Заполнение сущностей](entities.md).
6. [Заполнение интентов](intents.md).
7. [Тестирование сценария](test.md).

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней