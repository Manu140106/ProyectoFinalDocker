# Proyecto Final Docker — EAM

Arquitectura multi-contenedor con Java, Python, Node.js y MySQL orquestada con Docker Compose.

## Requisitos previos

- Docker Desktop instalado y corriendo

## Estructura del proyecto

    proyectoFinal/
    ├── db-init/
    │   └── init.sql
    ├── java-service/
    │   ├── Dockerfile
    │   ├── pom.xml
    │   └── src/
    ├── python-service/
    │   ├── Dockerfile
    │   ├── app.py
    │   └── requirements.txt
    ├── node-service/
    │   ├── Dockerfile
    │   ├── server.js
    │   └── packaje.json
    └── docker-compose.yml

## Levantar la solución

Desde la carpeta proyectoFinal/ ejecutar:

    docker compose up --build

Para correr en segundo plano:

    docker compose up --build -d

## Endpoints disponibles

| Servicio       | URL                              | Descripción              |
|----------------|----------------------------------|--------------------------|
| java-service   | http://localhost:8080/students   | Lista de estudiantes     |
| python-service | http://localhost:5000/stats      | Estadísticas             |
| node-service   | http://localhost:3000/report     | Reporte combinado        |

## IPs fijas asignadas

| Servicio       | IP           |
|----------------|--------------|
| db             | 172.20.0.2   |
| java-service   | 172.20.0.3   |
| python-service | 172.20.0.4   |
| node-service   | 172.20.0.5   |

## Red personalizada

- Nombre: universidad-net
- Tipo: bridge
- Subnet: 172.20.0.0/24
- Gateway: 172.20.0.1

## Volumen de persistencia

- Nombre: db-data
- Montado en: /var/lib/mysql

## Detener la solución

    docker compose down

Para eliminar también el volumen de la base de datos:

    docker compose down -v