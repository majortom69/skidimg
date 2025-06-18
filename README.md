## SkidIMG

**SkidIMG** это простое web-приложениея для редактирования, хостинга и публиакации изображений, а так же группировки их в альбом.
 
Ключевая фича заключается в том, что сервис автоматически определяет `User-agent`. Eсли пользователь делится ссылкой на изображние, например в Telegeam или Discord, 
то будет отправленна **оптимизированная версия** для быстрой загрузки
Если открыть ту же ссылку в браузере, то отображается **оригинал изобращения**.

---

## Стек

- **Язык**: Go
- **Роутинг**: [chi](https://github.com/go-chi/chi)
- **Обработка изображений**: [bimg](https://github.com/h2non/bimg) (на осове libvips)
- **База данных**: PosgreSQL
- **CI/CD**: Github Actions + Docker Compose

---

## 🚀 Автосборка и deploy

При каждом новом пуше в `main` происходит автоматическая сборка и deploy приложения с помощью [Github Actions](.github/workflows/deploy.yml) + [Docker Compose](docker-compose.yml)

---

## 🔗 Демо-ссылка

http://img.downgrad.com/

---

## Требования для запуска

- Go 1.18+ (рекомендуется 1.22+)
- PostgreSQL
- Docker + Docker Compose
- libvips 8.3+ (рекомендуется  8.8+)
- C-компилятор (к примеру gcc 4.6+ or clang 3.0+) для bimg

---

## Сборка Проекта

В первую очередь нужно создать `.env` в корне проекта
```env
POSTGRES_PASSWORD=your_postgres_password
JWT_SECRET_KEY=your_jwt_secret
``` 
Запуск через Docker Compose 
На Linux(затестированно на Ubuntu 22.04)
```sh
docker-compose up --build
```

На Windows
```sh
docker-compose up --build
```
