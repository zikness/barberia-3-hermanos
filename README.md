# Sistema de Reservas - Barbería "3 Hermanos"

## Descripción

Sistema de gestión de reservas para la barbería "3 hermanos" que automatiza la toma de horas, evita choques de agenda y mejora la experiencia tanto para clientes como para el personal interno.

## Problema que resuelve

La barbería necesitaba ordenar y automatizar la toma de horas para evitar:
- Choques de agenda
- Llamadas/WhatsApp manuales 
- Pérdidas de tiempo
- Sobreagendamiento

## Usuarios del sistema

- **Clientes**: Crear cuenta, reservar, reprogramar o cancelar citas
- **Barberos**: Ver agenda diaria/semanal, marcar asistencia, bloquear tiempos
- **Administrador**: Configurar horarios, gestionar servicios, ver métricas

## Tecnologías utilizadas

- **Backend**: Node.js con Express.js
- **Base de datos**: MongoDB con Mongoose
- **Caché**: Redis
- **Containerización**: Docker y Docker Compose
- **Control de versiones**: Git con Gitflow

## Arquitectura

- API REST con Express.js
- Base de datos MongoDB para persistencia
- Redis para caché de consultas frecuentes
- Sistema de roles y permisos
- Contenedores Docker para despliegue

## Funcionalidades principales

### MVP (Minimum Viable Product)
- Registro e inicio de sesión de clientes
- Agenda por barbero con bloques de 1 hora (08:00-20:00)
- Prevención de doble reserva
- Notificaciones de confirmación y recordatorios
- Panel interno para barberos y administrador

## Instalación y ejecución

### Prerrequisitos
- Docker y Docker Compose instalados
- Git instalado

### Pasos para ejecutar

git clone <repositorio>
cd <repositorio>
docker compose up --build


La API estará disponible en: `http://localhost:3000`

## Estructura del proyecto

/
├── src/
│ ├── controllers/
│ ├── models/
│ ├── routes/
│ └── middleware/
├── docker-compose.yml
├── Dockerfile
├── README.md
├── REQUERIMIENTOS.md
└── DISENO.md

-----------------------------------------------Gonza-------------------------------------------------
## Endpoints principales

- `POST /api/auth/register` - Registro de usuarios
- `POST /api/auth/login` - Inicio de sesión
- `GET /api/appointments` - Consultar citas
- `POST /api/appointments` - Crear nueva cita
- `PUT /api/appointments/:id` - Modificar cita
- `DELETE /api/appointments/:id` - Cancelar cita

## Reglas de negocio

- Horario de atención: 08:00 - 20:00, todos los días
- Duración por servicio: 1 hora
- Capacidad: 3 barberos simultáneos
- Cancelaciones permitidas hasta 2 horas antes

## Contribución

Este proyecto utiliza Gitflow:
- Rama principal: `main`
- Rama de desarrollo: `develop`  
- Features: `feature/gestion-de-reservas-online`

## Licencia

MIT License