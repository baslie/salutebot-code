# Документация JAICP Code

Полная документация по разработке приложений для виртуального ассистента Салют на платформе JAICP Code.

## О JAICP Code

JAICP Code — это платформа для создания голосовых и чат-приложений (SmartApps) на JavaScript. Она позволяет разрабатывать интеллектуальные диалоговые сценарии с использованием NLP-движка SmartApp Brain и интеграции с внешними сервисами.

### Ключевые возможности

- **JavaScript API** — мощный API для описания бизнес-логики и интеграций
- **SmartApp Brain** — технология определения смысла фраз с машинным обучением
- **SmartApp DSL** — декларативный язык для описания диалоговых сценариев
- **Модульная архитектура** — гибкая система модулей и компонентов
- **Интеграции** — встроенные сервисы для работы с внешними API

---

## Структура документации

### JavaScript API

Используйте JavaScript для описания бизнес-логики и интеграции с внешними системами.

- [Code](overview.md) — общий обзор платформы
- [Текущие дата и время в Code](current-datetime.md) — работа с датами и временем
- [JavaScript API в SmartApp DSL](js-api/overview.md) — обзор JavaScript API
- [Глобальный скоуп в Code](js-api/global-scope.md) — глобальные переменные
- [Структура JS-кода в Code](js-api/project-structure.md) — организация кода
- [Препроцессы и постпроцессы в Code](js-api/pre-post-process.md) — обработка запросов
- [Настройка времени сессии в приложении](js-api/session-lifetime-control.md) — управление сессиями
- [Превышение лимита объектов $session и $client в Code](js-api/overflow-session-client-data.md) — оптимизация данных

#### Functions

Глобальные функции для работы со строками, XML и логированием.

- [function bind(type, handler, path, name)](js-api/functions/bind-type-handler-path-name.md)
- [function capitalize(string)](js-api/functions/capitalize.md)
- [function currentDate()](js-api/functions/current-date.md)
- [function log(message)](js-api/functions/log-message.md)
- [function parseXml(xmlString)](js-api/functions/parse-xml.md)
- [function toPrettyString(obj)](js-api/functions/to-pretty-string.md)

#### Services

Встроенные сервисы для работы с NLP, HTTP, почтой и другими интеграциями.

- [GigaChat в Code](js-api/services/llm.md) — интеграция с GigaChat
- [smartGeo в Code](js-api/services/smartgeo.md) — геолокация
- [smartProfile в Code](js-api/services/smartprofile.md) — профили пользователей
- [smartPush в Code](js-api/services/smartpush.md) — push-уведомления
- [smartRating в Code](js-api/services/smartrating.md) — система рейтингов

##### Caila

Сервис для работы с NLP через SmartApp Brain.

- [function conformWithToken(text, number, token)](js-api/services/caila/conform-with-token.md)
- [function conform(text, number)](js-api/services/caila/conform.md)
- [function entitiesLookupWithToken(text, token)](js-api/services/caila/entities-lookup-with-token.md)
- [function entitiesLookup(text)](js-api/services/caila/entities-lookup.md)
- [function getEntityWithToken(text, token)](js-api/services/caila/get-entity-with-token.md)
- [function getEntity(text)](js-api/services/caila/get-entity.md)
- [function inferenceWithToken(text, settings, token)](js-api/services/caila/inference-with-token.md)
- [function inference(text, settings)](js-api/services/caila/inference.md)
- [function inflect(text, tag declension, token)](js-api/services/caila/inflect-with-token.md)
- [function inflect(text, tag declension)](js-api/services/caila/inflect.md)
- [function markupWithToken(text, token)](js-api/services/caila/markup-with-token.md)
- [function markup(text)](js-api/services/caila/markup.md)
- [function simpleInferenceWithToken(text, token)](js-api/services/caila/simple-inference-with-token.md)
- [function simpleInference(text)](js-api/services/caila/simple-inference.md)

##### Fetch

Современный сервис для работы с HTTP-запросами (альтернатива $http).

- [$fetch](js-api/services/fetch/overview.md) — обзор $fetch
- [$fetch.all(iterable)](js-api/services/fetch/all.md)
- [$fetch.allSettled(iterable)](js-api/services/fetch/allsettled.md)
- [$fetch.delete(url, settings)](js-api/services/fetch/delete.md)
- [$fetch.get(url, settings)](js-api/services/fetch/get.md)
- [$fetch.post(url, settings)](js-api/services/fetch/post.md)
- [$fetch.put(url, settings)](js-api/services/fetch/put.md)
- [$fetch.query(url, settings)](js-api/services/fetch/query.md)

##### Http

Классический сервис для работы с HTTP-запросами.

- [function checkUrls(method, urls, findFirst)](js-api/services/http/check-urls.md)
- [function check(method, urls)](js-api/services/http/check.md)
- [function config(settings)](js-api/services/http/config.md)
- [function delete(url, settings)](js-api/services/http/delete.md)
- [function get(url, settings)](js-api/services/http/get.md)
- [function post(url, settings)](js-api/services/http/post.md)
- [function put(url, settings)](js-api/services/http/put.md)
- [function query(url, settings)](js-api/services/http/query.md)
- [Кэширование http-вызовов](js-api/services/http/cache.md)

##### Jsapi

Утилиты для работы с датами, сессиями и вспомогательными функциями.

- [function currentTime()](js-api/services/jsapi/current-time.md)
- [function dateForZone(zone, format)](js-api/services/jsapi/date-for-zone.md)
- [$jsapi.levenshtein.distance](js-api/services/jsapi/levenshtein.md)
- [function newSession(object)](js-api/services/jsapi/new-session.md)
- [function random(max)](js-api/services/jsapi/random.md)
- [function resolvePath(basePath, relativePath)](js-api/services/jsapi/resolve-path.md)
- [function startSession()](js-api/services/jsapi/start-session.md)
- [function stopSession()](js-api/services/jsapi/stop-session.md)

##### Mail

Сервис для отправки email.

- [$mail](js-api/services/mail/overview.md) — обзор $mail
- [function debug(enabled)](js-api/services/mail/debug.md)
- [function sendMessage(address, subject, body)](js-api/services/mail/send-message.md)
- [function send(mailRequest)](js-api/services/mail/send.md)

##### Nlp

Встроенные NLP-утилиты для работы с текстом.

- [function checkMyVocabulary(word)](js-api/services/nlp/check-my-vocabulary.md)
- [function conform(word, number)](js-api/services/nlp/conform.md)
- [function fixKeyboardLayout(text)](js-api/services/nlp/fix-keyboard-layout.md)
- [function inflect(text, declension)](js-api/services/nlp/inflect.md)
- [function matchExamples(text, examples)](js-api/services/nlp/match-examples.md)
- [function matchPatterns(text, patterns)](js-api/services/nlp/match-patterns.md)
- [function match(text, state)](js-api/services/nlp/match.md)
- [function parseMorph(word)](js-api/services/nlp/parse-morph.md)
- [function tokenize(text)](js-api/services/nlp/tokenize.md)

##### Payment

Сервис для работы с платежами.

- [function checkPayment()](js-api/services/payment/checkpayment.md)
- [function clearItems()](js-api/services/payment/clearitems.md)
- [function getItems()](js-api/services/payment/getitems.md)

##### Reactions

Функции для формирования ответов приложения.

- [function answer(text)](js-api/services/reactions/answer.md)
- [function buttons(arg)](js-api/services/reactions/buttons.md)
- [function location(ll, lg)](js-api/services/reactions/location.md)
- [function newSession(arg)](js-api/services/reactions/new-session.md)
- [function pay(arg)](js-api/services/reactions/pay.md)
- [function random(arg)](js-api/services/reactions/random.md)
- [function transition(transition)](js-api/services/reactions/transition.md)

#### Variables

Глобальные переменные для доступа к контексту запроса и сессии.

- [Переменные JavaScript в Code](js-api/variables/overview.md) — обзор переменных
- [$client](js-api/variables/client.md) — данные клиента
- [$context](js-api/variables/context.md) — контекст диалога
- [$injector](js-api/variables/injector.md) — внедрение зависимостей
- [$parseTree](js-api/variables/parse-tree.md) — дерево разбора запроса
- [$request](js-api/variables/request.md) — входящий запрос
- [$response](js-api/variables/response.md) — формируемый ответ
- [$session](js-api/variables/session.md) — данные сессии
- [$sharedContext](js-api/variables/sharedcontext.md) — общий контекст
- [$temp](js-api/variables/temp.md) — временные данные

---

### SmartApp Brain (NLP)

Технология определения смысла фраз с машинным обучением.

- [SmartApp Brain](nlp/overview.md) — обзор технологии
- [Конвертеры в Code](nlp/converters.md) — преобразование данных

#### API

Прямой доступ к SmartApp Brain через HTTP API.

- [SmartApp Brain Direct API](nlp/api/overview.md) — обзор API
- [SmartApp Brain Direct API](nlp/api/smartapp-brain-direct-api.md) — детальное описание
- [analyze](nlp/api/analyze.md) — анализ текста
- [conform](nlp/api/conform.md) — согласование слов
- [inference](nlp/api/inference.md) — распознавание интентов
- [inferenceMultiple](nlp/api/inference-multiple.md) — пакетное распознавание
- [simpleInference](nlp/api/simple-inference.md) — упрощенное распознавание
- [entitiesLookup](nlp/api/entities-lookup.md) — поиск сущностей
- [inflect](nlp/api/inflect.md) — склонение слов
- [initialMarkup](nlp/api/initial-markup.md) — разметка текста
- [initialMarkupInternal](nlp/api/initial-markup-internal.md) — внутренняя разметка
- [trainNLU](nlp/api/train-nlu.md) — обучение модели
- [getNLUStatus](nlp/api/get-nlu-status.md) — статус обучения
- [getSpellerDictionary](nlp/api/get-speller-dictionary.md) — словарь проверки правописания
- [uploadSpellerDictionary](nlp/api/upload-speller-dictionary.md) — загрузка словаря
- [Экспорт проекта](nlp/api/export-project.md)
- [Импорт проекта](nlp/api/import-project.md)

**Работа с сущностями:**
- [Получить сущности проекта](nlp/api/list-entities.md)
- [Создать новую сущность](nlp/api/create-entity.md)
- [Получить именованную сущность](nlp/api/get-entity.md)
- [Получить сущность с записями по имени](nlp/api/get-entity-by-name.md)
- [Обновить именованную сущность](nlp/api/update-entity.md)
- [Обновить все сущности проекта](nlp/api/update-entities.md)
- [Удалить именную сущность](nlp/api/delete-entity.md)
- [Удалить список сущностей](nlp/api/delete-entities.md)

**Работа с записями сущностей:**
- [Получить словарь именованной сущности](nlp/api/get-entity-records.md)
- [Получить указанную запись из сущности](nlp/api/get-entity-record.md)
- [Создать новую запись в сущности](nlp/api/create-entity-record-by-entity-name.md)
- [Добавить запись в словарь сущности](nlp/api/create-entity-record.md)
- [Обновить указанную запись в сущности](nlp/api/update-entity-record.md)
- [Обновить запись в сущности](nlp/api/update-entity-record-by-entity-name.md)
- [Обновить все содержание сущности](nlp/api/update-all-entity-records.md)
- [Обновить содержание сущности](nlp/api/update-all-entity-records-by-entity-name.md)
- [Удалить указанную запись в сущности](nlp/api/remove-entity-record.md)
- [Удалить несколько записей](nlp/api/delete-records.md)
- [Удалить несколько записей](nlp/api/delete-records-by-entity-name.md)
- [Загрузить записи из файла](nlp/api/upload-records.md)

#### Brain в Code

Примеры использования SmartApp Brain в JavaScript-сценариях.

- [Пример использования SmartApp Brain](nlp/brain-in-code/overview.md)
- [Подготовка проекта Code для Brain](nlp/brain-in-code/project.md)
- [Входной сценарий для Brain в Code](nlp/brain-in-code/input-script.md)
- [Заполнение интентов Brain в Code](nlp/brain-in-code/intents.md)
- [Заполнение сущностей Brain в Code](nlp/brain-in-code/entities.md)
- [Сценарий опроса клиента Brain в Code](nlp/brain-in-code/loan-script.md)
- [Тестирование сценария Brain в Code](nlp/brain-in-code/test.md)

#### Classificator

Классификация текстов на основе семантической близости.

- [Классификатор STS](nlp/classificator/overview.md)
- [Подключение классификатора STS](nlp/classificator/connection-classificator.md)

#### Entities

Извлечение именованных сущностей из текста.

- [Сущности Brain](nlp/entities/overview.md)
- [Токены извлеченных сущностей в Brain](nlp/entities/ner.md)

#### Intents

Распознавание намерений пользователя.

- [Навигационные интенты](nlp/intents/navigational-intents.md)

#### Patterns

Паттерны для распознавания структурированного текста.

- [Паттерны в Code](nlp/patterns/about-patterns.md) — введение
- [Базовые элементы паттернов в Code](nlp/patterns/base-patterns.md)
- [Расширенные элементы паттернов в Code](nlp/patterns/advanced-patterns.md)
- [Именованные паттерны в Code](nlp/patterns/named-patterns.md)

#### Project

Настройка NLP-движка в проекте.

- [Настройка SmartApp Brain в Code](nlp/project/nlp-settings.md)
- [Расширенные настройки SmartApp Brain в классификаторе](nlp/project/advanced-classifer-settings.md)

#### Slot Filling

Извлечение слотов из запроса пользователя.

- [Слот-филлинг в Code и Brain](nlp/slot-filling/overview.md)
- [Заполнение слотов из запроса в Code и Brain](nlp/slot-filling/fields.md)
- [Прерывание слот-филлинга в Code и Brain](nlp/slot-filling/break.md)

---

### Project

Структура проекта и файлы конфигурации.

- [Обзор проекта Code](project/project-overview.md) — общий обзор
- [Файлы проекта](project/overview.md) — структура файлов
- [Настройка проекта в Code](project/project-settings.md) — конфигурация
- [Конфигурационный файл в Code](project/configuration-file.md) — caila.json
- [Файлы сценариев в Code](project/sc.md) — .sc файлы
- [Файлы JS-библиотек в Code](project/js.md) — .js файлы
- [Файлы с тестами в Code](project/xml.md) — .xml тесты
- [Работа с модулями в Code](project/modules.md) — модульность
- [Модули sys.modules в Code](project/sys-modules.md) — системные модули
- [Справочники именованных сущностей в Code](project/csv.md) — .csv файлы
- [Справочники YAML в Code](project/yaml.md) — .yaml файлы
- [Справочники меток в Code](project/tag-list.md) — теги
- [Поиск по файлам проекта Code](project/file-search.md) — навигация
- [Отладка приложения в Code](project/test-widget.md) — тестовый виджет
- [Логи сервера в Code](project/server-logs.md) — мониторинг

---

### Response

Формирование ответов приложения.

- [Формат ответа приложения в Code](response/overview.md)
- [Типы сообщений в Code](response/message-types.md)
- [Типы событий event](response/events-table.md)
- [Обработка запросов вне сценария Code](response/falty-request-processing.md)

---

### SmartApp DSL

Декларативный язык для описания диалоговых сценариев.

- [SmartApp DSL](sa-dsl/overview.md) — обзор языка

#### Tags

Теги для описания сценариев в декларативном стиле.

- [Декларативные теги SmartApp DSL](sa-dsl/tags/declarative-tags.md)
- [Теги интентов SmartApp DSL](sa-dsl/tags/intents-tags.md)
- [Теги реакций SmartApp DSL](sa-dsl/tags/reaction-tags.md)

---

### Templates

Готовые шаблоны приложений для быстрого старта.

- [Шаблоны приложений в Code](templates/smartapp-templates.md)

---

### Testing

Автоматическое тестирование диалоговых сценариев.

- [Автоматическое тестирование в Code](testing/tests-xml.md)
- [Теги тестирования в Code](testing/test-tags.md)
- [Тестирование слот-филлинга](testing/slot-filling-testing.md)

---

## Дополнительные ресурсы

- [Официальная документация JAICP](https://developers.sber.ru/docs/ru/va/code/overview)
- [Сообщество разработчиков](https://developers.sber.ru/community)
- [GitHub репозиторий](https://github.com/baslie/salutebot-code)

---

*Документация актуальна для платформы JAICP Code. Последнее обновление структуры: автоматически сгенерировано для 179 страниц.*
