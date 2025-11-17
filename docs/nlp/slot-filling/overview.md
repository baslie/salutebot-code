---
title: Слот-филлинг в Code и Brain
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/slot-filling/overview
reading_time: 1
badges:
- Code
- Brain
breadcrumbs:
- Что такое слот-филлинг
---

<!-- Бейджи: Code | Brain -->

# Слот-филлинг в Code и Brain

Обновлено 15 декабря 2023

[![](/assets/nlp/slot-filling/overview/Code.png)
Code](../../overview.md)[![](/assets/nlp/slot-filling/overview/Brain.png)
Brain](../overview.md)

Слот-филлинг (англ. slot filling) — процесс дозапроса данных для выполнения запроса пользователя. Полученные при дозапросе данные доступны в сценарии.

Слоты (англ. slots) — данные, которые клиент передает с запросом или в процессе дозапроса. У каждого слота есть обязательные атрибуты: `Имя`, `Тип`.

Модуль слот-филлинга подключается в [файле основного сценария](../../project/sc.md) с помощью тега [`require`](../../sa-dsl/tags/declarative-tags.md#require):

```
require: slotfilling/slotFilling.sc
  module = sys.zb-common
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней