# Spring Cloud Gateway – RequestRateLimiter Reproducer

This project is a minimal Spring Cloud Gateway application created to reproduce an issue where `RequestRateLimiter` is not found in a larger multi-module setup.

## ✅ Technologies

- Java 21
- Spring Boot
- Spring Cloud Gateway (WebFlux)
- Reactive Redis support
- IP-based rate limiting using `RequestRateLimiter`

## 📌 Problem Statement

With only Gateway + Redis, the application:

- Starts successfully
- Correctly registers `RequestRateLimiter`

The same configuration fails in a larger project when combined with:

- Spring Security
- OAuth2 Resource Server
- Eureka Client

## ▶️ Running the Application

```bash
mvn spring-boot:run
```

## ❗ Observed issue in original project

```
IllegalArgumentException: Unable to find GatewayFilterFactory with name RequestRateLimiter
```

This repository serves as a baseline comparison to highlight a possible dependency or auto-configuration interaction issue.
