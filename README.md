# Referral & Rewards Service

> In development

A Spring Boot backend for a customer referral programme. Users get referral codes, referred friends sign up and place orders, and rewards are credited automatically after fraud checks.

## Planned features

- JWT authentication (Spring Security)
- Unique referral code generation
- Referral sign-up and order tracking
- Reward ledger: PENDING → CREDITED / REJECTED
- Fraud rules using the Strategy pattern: no self-referral, duplicate-account check, reward caps
- Event-driven reward crediting from RabbitMQ order events
- Reward audit log in MongoDB
- Swagger / OpenAPI docs

## Tech stack

Java 17 · Spring Boot 3 · Spring Data JPA · MySQL · MongoDB · RabbitMQ · JUnit 5 · Mockito · Docker Compose · Kubernetes (Minikube) · GitHub Actions

## Architecture

Order event → RabbitMQ → Reward consumer → Fraud rules (Strategy) → Reward ledger (MySQL) + Audit log (MongoDB)
