# 🛡️ WallTrip Auth Service

Microservicio de **autenticación y autorización** para la plataforma **WallTrip**, desarrollado en **Swift + Vapor** siguiendo principios de **Clean Architecture**, con soporte para múltiples ambientes (`local`, `qa`, `stg`, `prod`).

---

## ✨ Características principales

- 🔑 **Gestión de usuarios**  
  - Registro de nuevos usuarios con validación de email único.  
  - Hashing seguro de contraseñas con **Bcrypt**.  
  - Repositorio de usuarios con CRUD básico.

- 🔐 **OAuth 2.1 / OIDC Ready**  
  - Soporte para `oauth_clients` (confidential y public).  
  - Almacenamiento seguro de client secrets (hashed).  
  - Preparado para flujos de `password`, `refresh_token` y `authorization_code+PKCE`.

- 🗄️ **Persistencia con PostgreSQL**  
  - Migraciones gestionadas
  - Tablas: `users`, `oauth_clients`, `consents`, `profiles`, `preferences`.

- ⚡ **Caching con Redis**  
  - Almacenamiento temporal de sesiones y tokens.  
  - Health check integrado.

- 🩺 **Health Endpoints**  
  - `GET /health/live` → estado básico de la app.  
  - `GET /health/ready` → verificación de **DB** y **Redis**.

- 🏗️ **Infraestructura lista para Docker**  
  - Imagen del microservicio.  
  - Imagen de **PostgreSQL**.  
  - Imagen de **Redis** para cache.  

---

## 🗂️ Estructura del proyecto

```bash
auth-service/
 ├─ README.md
 ├─ Package.swift
 ├─ Public/
 ├─ Sources/
 |   ├─ auth-service/
 |   |   ├─ Controllers/
 |   |   ├─ Migrations/
 |   |   ├─ Models/
 |   |   ├─ configure.swift
 |   |   ├─ entrypoint.swift
 |   |   ├─ routes.swift
 ├─ Tests/
 ├─ docker-compose.yml
 ├─ Dockerfile
 └─ Package.resolved
