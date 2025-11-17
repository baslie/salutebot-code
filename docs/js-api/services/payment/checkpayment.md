---
title: function checkPayment()
source_url: https://developers.sber.ru/docs/ru/va/code/js-api/services/payment/checkpayment
description: Документация для разработчиков | Разработка приложений для виртуального
  ассистента Салют
reading_time: 1
breadcrumbs:
- function checkPayment()
---

# function checkPayment()

Обновлено 11 апреля 2025

Для получения статуса платежа используется встроенная функция `$payment.checkPayment`, которая вызывает метод [`GET /invoices/{invoice_id}`](https://developers.sber.ru/docs/ru/va/about/monetization/payments/reference/get-invoice). Входным параметром для функции `$payment.checkPayment` является `invoice_id`.

Сохраните ответ с результатом статуса оплаты в отдельную переменную:

```
script: var response = $payment.checkPayment($session.invoice_id);
$session.invoice_status = response.invoice_status;
$reactions.answer($session.invoice_status);
```

В приведенном примере переменная `response` содержит весь ответ на запрос [`GET /invoices/{invoice_id}`](https://developers.sber.ru/docs/ru/va/about/monetization/payments/reference/get-invoice) со статусом платежа `invoice_status` и ошибкой `error`.



**Параметры ответа**

| Параметр | Описание |
| --- | --- |
| Code | Код ответа |
| Error | Блок с описанием ошибки или ответа |
| user\_message | Описание кода ошибки или ответа |
| error\_description | Техническое описание кода ошибки или ответа |
| error\_code | Код ответа |
| invoice\_id | Идентификатор счета, по которому был направлен запрос |
| invoice\_date | Дата и время создания счета |
| invoice\_status | Текущий статус счета. Возможные значения смотрите в разделе [Статусы платежа](https://developers.sber.ru/docs/ru/va/about/monetization/payments/statuses) |
| invoice | Блок с информацией по заказу. Передается только при коде ответа 200 |
| payment\_info | Блок с информацией о платеже |
| payment\_id | Идентификатор проведенной оплаты |
| card\_id | Токен карты, с которой была проведена оплата. Параметр возвращается, если использовалась сохраненная карта |
| name | Имя владельца карты, с которой была проведена оплата. Параметр возвращается, если использовалась сохраненная карта |
| masked\_pan | Маскированный номер карты, с которой была проведена оплата |
| expiry\_date | Срок действия карты, с которой была проведена оплата |
| cardholder | Имя владельца карты, с которой была проведена оплата |
| payment\_system | Платежная система, в которой зарегистрирована карта |
| payment\_system\_image. | Ссылка на логотип платежной системы |
| image | Ссылка на логотип карты в интерфейсе платежного устройства |
| paysys | Название платежного сервиса, через который был проведен платеж |
| paysys\_image | Ссылка на логотип платежного сервиса |
| bank\_info | Блок информации о банке плательщика |
| bank\_name | Название банка, выпустившего карту |
| bank\_country\_code | Код страны банка, выпустившего карту |
| bank\_country\_name | Название страны банка, выпустившего карту |
| bank\_image | Ссылка на логотип банка, выпустившего карту |

Заметили ошибку?

Выделите текст и нажмите `Ctrl` + `Enter`, чтобы сообщить нам о ней