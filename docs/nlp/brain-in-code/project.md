---
title: Подготовка проекта Code для Brain
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/brain-in-code/project
description: Подготовка проекта Code для Brain | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Brain
- Code
breadcrumbs:
- SmartApp Brain
- SmartApp Brain
- Подготовка проекта Code
---

<!-- Бейджи: Brain | Code -->

# Подготовка проекта Code для Brain

Обновлено 1 февраля 2024

[![](/assets/nlp/brain-in-code/project/Brain.png)
Brain](../overview.md)[![](/assets/nlp/brain-in-code/project/Code.png)
Code](../../overview.md)

NLU-ядро Brain — подключаемая функция платформы. Если для аккаунта включено использование NLU-ядра, в настройках проекта отображаются дополнительные параметры конфигурации.

1. В SmartApp Studio создайте проект [Code](https://developers.sber.ru/docs/ru/va/chat/script/project-creation#sozdanie-proekta-code) на основе шаблона [**Проект для SmartApp Brain**](../../templates/smartapp-templates.md#проект-для-smartapp-brain).
2. Убедитесь, что в конфигурационном файле `chatbot.yaml` заданы [параметры для работы со SmartApp Brain](https://developers.sber.ru/docs/ru/va/chat/voice-interface/command-recognition/nlu_core):

   ```
   # Название проекта. По умолчанию brain
   name: pizza-order
   # Основной сценарий, с которого начинается работа смартапа
   entryPoint:
       - main.sc
   botEngine: v2
   language: ru
   # Порог срабатывания классификатора. Рекомендуется настраивать в зависимости от выбранного алгоритма
   caila:
       noMatchThreshold: 0.2
   ```
3. Убедитесь, что в основном сценарии `main.sc` подключен модуль слот-филлинга и сценарий опроса пользователя `order.sc`.
4. В папке `src/themes` создайте файл сценария `order.sc`, который будет отвечать за [прием заказа](loan-script.md).

Здесь мы подключаем [модуль слот-филлинга](../slot-filling/overview.md) и файл со сценарием дозапроса `order.sc`.

Далее приступайте к созданию [входного сценария смартапа `main.sc`](input-script.md).

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней