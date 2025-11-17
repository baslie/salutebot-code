---
title: Тестирование сценария Brain в Code
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/brain-in-code/test
description: Тестирование сценария Brain в Code | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Brain
- Code
breadcrumbs:
- SmartApp Brain
- SmartApp Brain
- Тестирование сценария
---

<!-- Бейджи: Brain | Code -->

# Тестирование сценария Brain в Code

Обновлено 20 декабря 2023

[![](/assets/nlp/brain-in-code/test/Brain.png)
Brain](../overview.md)[![](/assets/nlp/brain-in-code/test/Code.png)
Code](../../overview.md)

Для тестирования сценария смартапа перейдите *Редактор* > *Сценарии* > запустите тестовый виджет, нажав в нижнем правом углу кнопку *Тестировать.*

Далее рассмотрим основные кейсы нашего сценария:

1. Ассистент приветствует клиента и по-разному реагирует, в зависимости от того, был ли заполнен слот для сущности `@pymorphy.name` (распозналось ли имя):

![slots](/assets/nlp/brain-in-code/test/test-1-af9afdd68d3dd450ad79e832e77ac2d5.png)
![slots](/assets/nlp/brain-in-code/test/test-2-89ba2cff5224c4bd18151c2173296068.png)

2. Клиент выражает свое намерение `заказать пиццу`, но при этом этих данных недостаточно для движения далее по сценарию, так как слоты сущностей `@PizzaName`, `@PizzaSize` и `@PizzaCount` не заполнены. При помощи слот-филлинга мы дозапрашиваем информацию у клиента.

![slots](/assets/nlp/brain-in-code/test/test-3-65d5bc84e619886282452ae15c375347.png)

3. После того, как все слоты были заполнены, смартап возвращается к основному сценарию. Здесь будет выведена вся собранная информация.

![slots](/assets/nlp/brain-in-code/test/test-4-161f381bf08732c21bcb26463cde0293.png)

[Напишите тесты на сценарий смартапа](../../testing/tests-xml.md).

4. Приступайте к процедуре [публикации смартапа](https://developers.sber.ru/docs/ru/va/about/publication/app-publication).

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней