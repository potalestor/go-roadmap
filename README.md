# 🚀 3-месячный Roadmap до уровня Senior Golang Developer

---

# Месяц 1 — Go Internals + Concurrency

## 🎯 Цели
- Понять внутренности языка
- Освоить конкурентность
- Наладить работу с ключевыми пакетами стандартной библиотеки
- Сделать первый мини-проект с очередью задач

---

## 📌 Неделя 1 — Go Internals

### Теория
- [ ] Go Memory Model  
- [ ] Внутренности GC (tri-color, pacer, generational ideas)  
- [ ] GMP модель (goroutine scheduler)  
- [ ] Механика syscalls и netpoller  
- [ ] Структура slice/map/channel изнутри  

### Практика
- [ ] Реализовать свой worker-pool  
- [ ] Провести benchmark: goroutines vs workers  
- [ ] Снять CPU/MEM профили простого сервиса  
- [ ] Разобраться с flamegraph  

---

## 📌 Неделя 2 — Concurrency Mastery

### Теория
- [ ] Типы каналов и их поведение  
- [ ] Mutex/RWMutex/Atomic  
- [ ] WaitGroup/Once/Cond  
- [ ] Race conditions, deadlocks  

### Практика
- [ ] Pipeline c fan-in/fan-out  
- [ ] Реализация rate limiter (token bucket)  
- [ ] Использовать `go test -race` на проекте  
- [ ] Найти и исправить race-condition  

---

## 📌 Неделя 3 — Стандартная библиотека

### Теория
- [ ] net/http: middleware, transport tuning, timeouts  
- [ ] context: cancel/deadline propagation  
- [ ] io, bufio, os  
- [ ] encoding/json и альтернативы  
- [ ] errors + wrapping  

### Практика
- [ ] HTTP сервер с graceful shutdown  
- [ ] Кастомный JSON encoder (минимум аллокаций)  
- [ ] Продвинутая работа с bufio/Reader/Writer  

---

## 📌 Неделя 4 — Проект месяца

### Мини-проект: Concurrent Task Processor  
- [ ] Очередь задач (in-memory или Redis)  
- [ ] Рабочие (goroutines pool)  
- [ ] REST API для постановки задач  
- [ ] Прогресс задач + статус  
- [ ] Graceful shutdown  
- [ ] pprof + Prometheus метрики  

---

# Месяц 2 — Архитектура, базы данных, performance

## 🎯 Цели
- Понять архитектуры уровня senior
- Научиться эффективно работать с SQL/NoSQL
- Освоить gRPC и брокеры сообщений
- Проводить профилирование и оптимизацию

---

## 📌 Неделя 5 — Архитектуры

### Теория
- [ ] Clean Architecture  
- [ ] DDD: entities, aggregates, bounded context  
- [ ] Modular Monolith  
- [ ] Микросервисы: best practices  

### Практика
- [ ] Организовать проект по Clean Architecture  
- [ ] Настроить DI (wire/fx)  
- [ ] Разделить слой команд/запросов (CQRS-light)  

---

## 📌 Неделя 6 — Базы данных

### Теория
- [ ] Индексы, их виды  
- [ ] План выполнения запросов  
- [ ] MVCC  
- [ ] Транзакции, уровни изоляции  
- [ ] Блокировки (row-level locks)  

### Практика
- [ ] Написать проект с SQLC или go-pg  
- [ ] Оптимизировать SELECT через EXPLAIN ANALYZE  
- [ ] Добавить connection pooling  
- [ ] Batch-insert / UPSERT / bulk операции  

---

## 📌 Неделя 7 — gRPC + Kafka/NATS

### Теория
- [ ] Protocol Buffers  
- [ ] Unary/streaming RPC  
- [ ] Interceptors  
- [ ] Event-driven design  
- [ ] Basics Kafka/NATS: partitions, consumer groups  

### Практика
- [ ] Реализовать сервис на gRPC  
- [ ] Добавить streaming endpoint  
- [ ] gateway → REST  
- [ ] Подписчик Kafka/NATS (consumer group)  

---

## 📌 Неделя 8 — Performance & Profiling

### Теория
- [ ] pprof (CPU, MEM, allocs, mutex)  
- [ ] trace  
- [ ] Flamegraphs  
- [ ] Reducing allocations  
- [ ] sync.Pool  
- [ ] Lock contention analysis  

### Практика
- [ ] Снять и проанализировать CPU профили  
- [ ] Уменьшить количество аллокаций в проекте  
- [ ] Найти bottleneck по locks  
- [ ] Улучшить latency и throughput  

---

# Месяц 3 — DevOps, K8s, Observability, Security, финальный проект

## 🎯 Цели
- Научиться деплоить и сопровождать сервисы
- Понять Kubernetes
- Настроить полную наблюдаемость
- Сделать production-level проект

---

## 📌 Неделя 9 — Docker + CI/CD

### Теория
- [ ] Multi-stage builds  
- [ ] Distroless  
- [ ] GitHub Actions / GitLab CI  
- [ ] Линтеры и тесты в pipeline  

### Практика
- [ ] Оптимизировать контейнер (<20MB)  
- [ ] CI pipeline: lint → test → build → push  
- [ ] Автодеплой (ArgoCD / GitOps basic)  

---

## 📌 Неделя 10 — Kubernetes

### Теория
- [ ] Deployment / StatefulSet  
- [ ] Service / Ingress  
- [ ] ConfigMap / Secret  
- [ ] HPA / autoscaling  
- [ ] Lifecycle hooks  
- [ ] readiness/liveness  

### Практика
- [ ] Задеплоить сервис в kind/minikube  
- [ ] Настроить autoscaling на метрики  
- [ ] Blue/green или canary deploy (базово)  

---

## 📌 Неделя 11 — Observability + Security

### Теория
- [ ] OpenTelemetry (traces/metrics/logs)  
- [ ] Prometheus  
- [ ] Grafana  
- [ ] Jaeger/Tempo  
- [ ] JWT, OAuth2  
- [ ] TLS/mTLS basics  

### Практика
- [ ] Добавить traces + метрики в проект  
- [ ] Создать дашборды в Grafana  
- [ ] Настроить алерты  
- [ ] Включить mTLS между двумя сервисами  

---

## 📌 Неделя 12 — Финальный Senior-level проект

### Цель: создать production-ready high-load систему  
**High-throughput event ingestion service**

### Функционал:
- [ ] REST/gRPC ingestion endpoint  
- [ ] Очередь: Kafka/NATS  
- [ ] Воркеры с backpressure  
- [ ] Асинхронная запись в ClickHouse / PostgreSQL  
- [ ] Поддержка batch operations  
- [ ] Полный набор метрик  
- [ ] Трейсинг всех запросов  
- [ ] CI/CD  
- [ ] Деплой в Kubernetes  
- [ ] Дашборды + алерты  

