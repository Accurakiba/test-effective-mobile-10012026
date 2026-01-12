```mermaid
flowchart TD
  User[Пользователь] --> App[Мобильное приложение]

  App -->|Разрешение на пуши| Token[Push token]
  Token --> Backend[Backend]

  Backend -->|Хранение токена\n(user_id ↔ token)| Storage[Хранилище токенов]

  Cart[Сервис корзины] -->|Событие| Notify[Сервис уведомлений]
  Order[Сервис заказа] -->|Событие| Notify

  Notify -->|Формирование текста пуша| Push[Push уведомление]
  Push --> FCM[FCM (Android)]
  Push --> APNs[APNs (iOS)]

  FCM --> App
  APNs --> App