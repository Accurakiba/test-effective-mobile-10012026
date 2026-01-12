# Блок-схема отправки пушей

```mermaid
flowchart TD
  User[Пользователь] --> App[Мобильное приложение]

  App -->|Разрешает пуши| Token[Push token]
  Token --> Backend[Backend]

  Backend --> Storage[Хранилище токенов\n(user_id - token)]

  Cart[Сервис корзины] -->|Событие| Notify[Сервис уведомлений]
  Order[Сервис заказа] -->|Событие| Notify

  Notify -->|Формирует текст пуша| Push[Push уведомление]
  Push --> FCM[FCM (Android)]
  Push --> APNs[APNs (iOS)]

  FCM --> App
  APNs --> App
