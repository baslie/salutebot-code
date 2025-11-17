---
title: Навигационные интенты
source_url: https://developers.sber.ru/docs/ru/va/code/nlp/intents/navigational-intents
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
badges:
- Code
breadcrumbs:
- Навигационные интенты
toc:
- title: Дальше
  level: 2
  id: dalshe
- title: Вверх или Вниз
  level: 2
  id: vverh-ili-vniz
- title: Влево или Вправо
  level: 2
  id: vlevo-ili-vpravo
- title: Пример обработки навигационной команды на фронтенде
  level: 2
  id: primer-obrabotki-navigatsionnoy-komandy-na-frontende
---

<!-- Бейджи: Code -->

# Навигационные интенты

Содержание раздела

* [Дальше](#дальше)
* [Вверх или Вниз](#вверх-или-вниз)
* [Влево или Вправо](#влево-или-вправо)
* [Пример обработки навигационной команды на фронтенде](#пример-обработки-навигационной-команды-на-фронтенде)

# Навигационные интенты

Обновлено 15 декабря 2023

[![](/assets/nlp/intents/navigational-intents/Code.png)
Code](../../overview.md)

Навигационные интенты инициируют команды, которые ассистент использует для прокрутки экранов смартапа. Навигационные интенты актуальны только для [Canvas App](https://developers.sber.ru/docs/ru/va/canvas/title-page).

## Дальше

Обнаружив интент, ассистент прокрутит экран смартапа вправо или вниз, в зависимости от основного направления прокрутки экранов.

Интенты для перехода к следующему экрану:

* Вперед;
* Дальше;
* Далее;
* Следующая;
* Следующая страницы;
* Покажи следующую;
* Покажи еще.

Ассистент передает команду на фронтенд смартапа в следующем виде:

```
{
    "items": [
        {
            "command": {
                "type": "navigation",
                "navigation": {
                    "command": "FORWARD"
                    // другие параметры, необходимые для команды
                }
            }
        }
    ]
}
```

## Вверх или Вниз

Обнаружив интент, ассистент прокрутит экран смартапа вверх или вниз.

Интенты для прокрутки экрана вверх:

* Вверх;
* Прокрути вверх;
* Выше.

Команда передается на фронтенд в следующем виде:

```
{
    "items": [
        {
            "command": {
                "type": "navigation",
                "navigation": {
                    "command": "UP"
                    // другие параметры, необходимые для команды
                }
            }
        }
    ]
}
```

Интенты для прокрутки экрана вниз:

* Вниз;
* Прокрути вниз;
* Опусти;
* Ниже.

Команда передается на фронтенд в следующем виде:

```
{
    "items": [
        {
            "command": {
                "type": "navigation",
                "navigation": {
                    "command": "DOWN"
                    // другие параметры, необходимые для команды
                }
            }
        }
    ]
}
```

## Влево или Вправо

Обнаружив интент, ассистент прокрутит экран смартапа вправо или влево.

Интенты для прокрутки экрана влево:

* Влево;
* В лево;
* Налево;
* На лево.

Команда передается на фронтенд в следующем виде:

```
{
    "items": [
        {
            "command": {
                "type": "navigation",
                "navigation": {
                    "command": "LEFT"
                    // другие параметры, необходимые для команды
                }
            }
        }
    ]
}
```

Интенты для прокрутки экрана вправо:

* Вправо;
* В право;
* Направо;
* На право.

Команда передается на фронтенд в следующем виде:

```
{
    "items": [
        {
            "command": {
                "type": "navigation",
                "navigation": {
                    "command": "RIGHT"
                    // другие параметры, необходимые для команды
                }
            }
        }
    ]
}
```

## Пример обработки навигационной команды на фронтенде

Поддержите навигационные команды на фронтенде своего смартапа. Например, с помощью Assistant Client.

/src/utils/assistant.ts

```
export const dataHandler = (command: AssistantClientCustomizedCommand<AssistantSmartAppData>) => {
 let navigation: AssistantNavigationCommand['navigation'] | undefined;

switch (command.type) {

   ...

    // Обработка навигационной команды
    case 'navigation':
        navigation = (command as AssistantNavigationCommand).navigation;
        break;
 }

 // Обработка навигационных команд
 if (navigation) {
    switch (navigation.command) {
        case 'UP':
            window.scrollTo(0, window.scrollY - 500);
            break;
        case 'DOWN':
            window.scrollTo(0, window.scrollY + 500);
            break;
        default:
            break;
    }
 }
};
```

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней