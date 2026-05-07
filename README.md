# Backend Ventas - Innovatech Chile

API REST desarrollada en Spring Boot con Java 17 para gestionar las ventas de productos.

## Tecnologías
- Java 17
- Spring Boot 3.4.4
- MySQL 8.0
- Docker (multi-stage build)
- GitHub Actions (CI/CD)

## Requisitos
- Docker Desktop
- Docker Compose

## Variables de entorno
| Variable | Descripción | Ejemplo |
|---|---|---|
| DB_ENDPOINT | Host de la base de datos | localhost |
| DB_PORT | Puerto de la base de datos | 3306 |
| DB_NAME | Nombre de la base de datos | ventas_db |
| DB_USERNAME | Usuario de la base de datos | root |
| DB_PASSWORD | Contraseña de la base de datos | Admin1234! |

## Cómo ejecutar localmente

1. Clonar el repositorio:
```bash
git clone https://github.com/AAagustinnn/backend-ventas.git
cd backend-ventas
```

2. Crear archivo `.env` basado en `.env.example`:
```bash
cp .env.example .env
```

3. Levantar los contenedores:
```bash
docker compose up --build
```

4. Verificar que funciona:
http://localhost:8080/swagger-ui.html

## Pipeline CI/CD
El pipeline se activa automáticamente al hacer push en la rama `deploy`:
- Build de la imagen Docker
- Push a Docker Hub
- Despliegue automático en EC2

## Endpoints principales
- `GET /api/v1/ventas` - Obtener todas las ventas
- `POST /api/v1/ventas` - Crear una venta
- `GET /api/v1/ventas/{id}` - Obtener venta por ID
- `PUT /api/v1/ventas/{id}` - Actualizar venta
- `DELETE /api/v1/ventas/{id}` - Eliminar venta