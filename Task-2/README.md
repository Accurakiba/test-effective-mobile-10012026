# Решение задачи №2

---

## Пример запроса к REST API
```http
GET /api/v1/partners/stores  
Host: api.petrushka-green.ru  
Authorization: Bearer <access_token>  
Accept: application/json
```

---

## Пример ответа REST API в JSON формате  

```json
{
  "stores": [
    {
      "id": 1,
      "name": "METRO",
      "logo_url": "https://cdn.petrushka-green.ru/logos/metro.png",
      "delivery_type": "scheduled",
      "delivery_time_from": "21:00",
      "delivery_time_to": "23:00",
      "delivery_text": "Ближайшая доставка сегодня 21:00–23:00",
      "external_url": "https://www.metro.ru"
    },
    {
      "id": 2,
      "name": "Ашан",
      "logo_url": "https://cdn.petrushka-green.ru/logos/ashan.png",
      "delivery_type": "scheduled",
      "delivery_time_from": "18:00",
      "delivery_time_to": "20:00",
      "delivery_text": "Ближайшая доставка сегодня 18:00–20:00",
      "external_url": "https://www.ashan.ru"
    },
    {
      "id": 3,
      "name": "ВкусВилл",
      "logo_url": "https://cdn.petrushka-green.ru/logos/vkusvill.png",
      "delivery_type": "fast",
      "delivery_time_min": 20,
      "delivery_time_max": 60,
      "delivery_text": "Быстрая доставка от 20 до 60 минут",
      "external_url": "https://vkusvill.ru"
    },
    {
      "id": 4,
      "name": "Виктория",
      "logo_url": "https://cdn.petrushka-green.ru/logos/victoria.png",
      "delivery_type": "scheduled",
      "delivery_time_from": "17:00",
      "delivery_time_to": "19:00",
      "delivery_text": "Ближайшая доставка сегодня 17:00–19:00",
      "external_url": "https://victoria.ru"
    }
  ]
}
```

- по моему мнению, поле `delivery_text` собирается на backend'e на основе `delivery_time_*`  
- так же, предполагаю, что что время доставки берётся из заранее заданных условий партнёра (SLA) и хранится в базе партнёрских магазинов