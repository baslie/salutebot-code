---
title: SmartApp Brain Direct API
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/api/overview
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
breadcrumbs:
- SmartApp Brain
- SmartApp Brain
- SmartApp Brain Direct API
toc:
- title: Аутентификация
  level: 2
  id: autentifikatsiya
---

# SmartApp Brain Direct API

Содержание раздела

* [Аутентификация](#аутентификация)

# SmartApp Brain Direct API

Обновлено 20 февраля 2025

С помощью SmartApp Brain Direct API вы можете использовать сторонний обученный классификатор в своих проектах. Для обращения к SmartApp Brain Direct API из проектов, разработанных в Code, используйте встроенный сервис [`$caila`](../../js-api/services/caila/markup-with-token.md).

Если переобучение модели не удалось, то для классификации будет использоваться предыдущая версия.

## Аутентификация

Для подтверждения запросов используется API-ключ Brain.

Чтобы получить ключ:

1. Откройте проект Code.
2. Перейдите в раздел **Настройки проекта**.
3. Откройте вкладку **Классификатор**.
4. Сгенерируйте ключ в поле **API-ключ Brain**.
5. Скопируйте ключ.

Для получения API-ключа текущего проекта в сценарии используйте метод `$jsapi.cailaService.getCurrentClassifierToken()`.

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней