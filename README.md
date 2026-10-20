# Привет! Я Дарья 👋

**Backend-разработчик (Go / Python / C#)**

Выпускница МАИ 2026 года (красный диплом), специальность «Информатика и вычислительная техника». 
Ищу стажировку или junior-позицию в области backend-разработки, DevOps или сетевой инженерии. 
Готова решать сложные задачи, разбираться в legacy-коде и учиться новому.

---

## 🛠 Мой стек

Здесь я не просто перечисляю технологии, а показываю, **как** я их использую на практике.

**Языки:**
`Go` `Python` `C#` `C++` `SQL` `JavaScript` `Bash`

**Архитектура и Backend:**
`Gin` `FastAPI` `ASP.NET Core` `REST API` `Микросервисы` `SOLID` `context.Context` `Graceful Shutdown`

**Базы данных и миграции:**
`PostgreSQL (pgx/pgxpool)` `Redis (кэширование)` `Оптимизация запросов` `EXPLAIN ANALYZE` `Миграции (goose)` `EF Core`

**Безопасность:**
`JWT (валидация алгоритма)` `bcrypt` `CORS` `Trusted Proxies`

**Надежность и Observability:**
`Liveness/Readiness пробы` `Health-checks` `Таймауты HTTP-сервера` `Логирование (slog + request-id)`

**DevOps и инфраструктура:**
`Docker` `Docker Compose` `Kubernetes (minikube)` `GitLab CI` `GitHub Actions` `Nginx` `Linux`

**Сети:**
`TCP/IP` `DHCP` `DNS` `VLAN` `GNS3` `Wireshark` `Nmap`

---

## 🚀 Ключевые проекты

### [Smart Image Lab (Дипломный проект)](https://github.com/DariaVerseau/diploma)
*Микросервисное приложение для обработки изображений.*

- **Стек:** Go (Gin), Python (FastAPI, PyTorch), React (Vite, Tailwind), PostgreSQL, Docker, nginx, GitHub Actions (CI), GHCR.
- **Архитектура и БД:** Спроектировала схему БД с `UUID`, `BIGSERIAL` и `TIMESTAMPTZ`. Настроила миграции через `goose` (DDL вынесен в отдельный сервис `migrate`, образ зафиксирован по digest). Добавила композитный индекс `(user_id, created_at DESC)`, проверила через `EXPLAIN ANALYZE`. Настроила пул соединений `pgxpool` (`MaxConns=25`, `MinConns=5`, `MaxConnLifetime=1h`).
- **Безопасность:** JWT через `TokenManager` (DI), валидация секретов (fail-fast), проверка алгоритма подписи (**защита от alg confusion**), маппинг ошибок (sentinel errors + `errors.Is`).
- **Production-практики:** Graceful Shutdown (`SIGTERM`, таймауты `http.Server`), health-checks `/health` (liveness) и `/ready` (readiness) с параллельной проверкой БД и ML (timeout 1s). Dockerfile: multi-stage, non-root, `HEALTHCHECK`. Docker Compose: digest, `depends_on` с условиями.
- **CI (GitHub Actions):** `go vet`, `go test -race -cover`, `govulncheck`, сборка и push Docker-образа в GHCR с кэшированием. *(CD — в планах: деплой в K8s).*
- **Нагрузочное тестирование (ApacheBench):** `/health` — 1692 RPS, `/images` (JWT) — 1318 RPS, `/login` (bcrypt) — 46 RPS. Выявила **bcrypt как CPU-bound узкое место** login/register (110 ms), обосновала rate limiting и горизонтальное масштабирование.

### [InventoryWarehouseAPI](https://github.com/DariaVerseau/InventoryWarehouseAPI)
*Программа учёта складского инвентаря.*
- **Стек:** C# (ASP.NET Core, EF Core), PostgreSQL, Clean Architecture.
- **Что сделано:** Реализовала REST API с CRUD, пагинацией, фильтрацией и PATCH-запросами. Настроила JWT-аутентификацию и Repository Pattern.

### [Frontend для дипломного проекта](https://github.com/DariaVerseau/FrontendReactForDiploma)
*SPA на React для взаимодействия с API.*
- **Стек:** React, Vite, Tailwind, Docker, Nginx.
- **Что сделано:** Разработала интерфейс (авторизация, личный кабинет, пагинация). Настроила сборку и контейнеризацию.

### [WebPrLab1](https://github.com/DariaVerseau/WebPrLab1)
*React-приложение с CI/CD.*
- **Стек:** React, Vite, Docker, Nginx, GitHub Actions.
- **Что сделано:** Настроила пайплайн CI/CD через GitHub Actions (сборка, тестирование, Docker, деплой).

---

## 📫 Как со мной связаться

- **Email:** daryakapustyanskaya@yandex.ru
- **Telegram:** [@darina_reyyy](https://t.me/darina_reyyy)
