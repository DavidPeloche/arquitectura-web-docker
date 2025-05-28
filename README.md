# Proxecto Docker con mounts e volume

Arquitectura web con frontend, backend e base de datos. Inclúe persistencia e montaxes de código en tempo real.

# Arquitectura Web con Docker

## Descripción

Este proyecto implementa una arquitectura web básica compuesta por:

- **Frontend:** Servido con Nginx, mostrando una página HTML estática.
- **Backend:** Aplicación Python con Flask, expuesta en el puerto 5000.
- **Base de datos:** PostgreSQL con persistencia mediante un volume Docker.

Se utilizan **bind mounts** para cargar el código fuente directamente desde el host y un **volume Docker** para garantizar la persistencia de datos en la base de datos.

## Composición de los servicios

- **frontend:** Utiliza la imagen `nginx:alpine`, monta el código estático con bind mount, escucha en el puerto 8080.
- **backend:** Construido desde un Dockerfile basado en Debian, corre la app Flask, expuesto en el puerto 5000, con bind mount para el código.
- **db:** Imagen oficial de PostgreSQL, usa un volume para almacenar datos persistentes.

## Comandos principales

- Levantar los servicios:
  docker compose up

- Parar los servicios:
  docker compose down

- Ver logs del backend:
  docker compose logs backend

