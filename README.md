
***

## 3) `gowo-infra/README.md`

```md
# GoWo - Infraestructura (Docker & Base de Datos)

Este repositorio contiene la **capa de Infraestructura y Datos** del proyecto GoWo. Aquí se definen los contenedores Docker y la configuración de la base de datos para GoWo.

## Objetivo del repositorio

- Definir la base de datos de GoWo (PostgreSQL) y su persistencia.
- Mantener archivos de infraestructura (por ejemplo: `docker-compose.yml`).
- Mantener el repositorio **independiente** del código de frontend y backend.

## Tecnologías principales

- Docker
- Docker Compose
- PostgreSQL (motor de base de datos)
- Volúmenes de Docker para persistencia de datos

## Arquitectura de Datos

- Motor de BD: **PostgreSQL**.
- Puerto interno de la base de datos: **5432**.
- Persistencia: volumen de Docker (por ejemplo `gowo_db_data`).
- El backend se conectará usando `DATABASE_URL` o variables equivalentes.

## Ejemplo de `docker-compose.yml` (a completar por el equipo)

> Nota: Este archivo es solo una base; el equipo deberá ajustarlo.

```yaml
version: "3.9"

services:
  gowo-db:
    image: postgres:16
    container_name: gowo-db
    restart: always
    environment:
      POSTGRES_USER: gowo_user
      POSTGRES_PASSWORD: gowo_password
      POSTGRES_DB: gowo_db
    ports:
      - "5432:5432"
    volumes:
      - gowo_db_data:/var/lib/postgresql/data

volumes:
  gowo_db_data:
