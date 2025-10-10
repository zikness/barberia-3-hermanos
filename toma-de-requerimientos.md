# Toma de Requerimientos - Barbería "3 Hermanos"
## Objetivo
 - Problema del negocio: La barbería necesita ordenar y automatizar la toma de horas para evitar choques de agenda, llamadas/WhatsApp manuales y pérdidas de tiempo.


 - Qué espera el cliente: Una aplicación sencilla y ordenada para que clientes creen cuenta, reserven, reprogramen o cancelen una hora, elijan barbero y reciban recordatorios.


 - Usuarios: Clientes (externos) y personal interno (barberos y administrador/encargado).


 - Mínimo indispensable: Registro/login de clientes, agenda por barbero con bloques de 1 hora entre 08:00 y 20:00, prevención de doble reserva, y notificaciones de confirmación.


## Contexto del negocio
 - Horario: Lunes–Domingo (asumido, confirmar en reunión) de 08:00 a 20:00.


 - Duración estándar por servicio: 1 hora por corte.


 - Capacidad: 3 barberos, cada uno con la misma disponibilidad.


 - Canales actuales: Agenda manual (llamadas/WhatsApp) — propenso a errores y sobreagendamiento.

## Usuarios y roles 
 - Cliente: crea cuenta, inicia sesión, ver disponibilidad, agenda/reagenda/cancela, recibe notificaciones.


 - Barbero: ve su agenda diaria/semanal, marca asistencia/estado, bloquea tiempos (descanso/ausencia).


- Administrador: configura horarios globales y por barbero, gestiona servicios y precios, ve métricas básicas, administra usuarios.

## Funcionalidades

# Gestión de cuentas
 - Registro e inicio de sesión (email + contraseña).

 - Perfil básico de cliente (nombre, teléfono).


# Agenda y reservas
 - Calendario por barbero y vista “todos”.

 - Bloques de tiempo de 1 hora; rango 08:00–20:00.

 - Evitar doble reserva: un bloque puede estar ocupado por un solo cliente por barbero.

 - Selección de barbero o “cualquiera” (asigna automáticamente el primer barbero disponible).

 - Confirmación de reserva y número/ID de la cita.

 - Reagendar/cancelar por parte del cliente (con regla de mínima antelación, p. ej. 2 horas — confirmar).


# Notificaciones
 - Confirmación inmediata (in-app y email).


 - Recordatorio automático (por ejemplo, 24 h y 2 h antes).


# Panel interno
 - Vista diaria/semanal por barbero.


 - Bloqueo manual de slots (descanso/ausencia).


 - Listado del día con estado (Pendiente, Confirmada, Completada, No asistió).

## Requisitos legales y normativos
 - Cumplimiento de la Ley de Protección de Datos Personales (según normativa local).


 - Solicitud de consentimiento explícito para el uso de datos de contacto.


 - Almacenamiento seguro de datos personales en servidores certificados.


 - Notificación al usuario en caso de incidentes de seguridad que comprometan su información

## Reglas de negocio 
 - Un bloque de 1 hora reservado por un cliente/barbero no puede ser asignado a otro hasta que sea cancelado.


 - La barbería funciona entre 08:00–20:00 con cortes de 1 h.


 - 3 barberos, máximo 3 citas en paralelo.


 - Cancelaciones: deben hacerse al menos 2 h antes.


 - Tipos de pago: efectivo y transferencia (por ahora fuera del MVP, pero considerado en reglas).

## Datos a almacenar
 - Tablas principales y atributos mínimos:
 Usuario (Cliente): id, nombre, email, teléfono, fecha_registro.

 - Barbero: id, nombre, disponibilidad, horario_base.

 - Cita: id, cliente_id, barbero_id, fecha, hora_inicio, hora_fin, estado (pendiente, confirmada, cancelada, completada).

 - Administrador: id, nombre, email.

 - Servicios (futuro): id, nombre, duración, precio.

 - Diferencias: clientes crean citas, barberos solo gestionan disponibilidad, administrador gestiona todo.


## Requisitos no funcionales
 - Aplicación web responsive (usable en móvil y escritorio).

 - Seguridad: contraseñas encriptadas, sesiones seguras.

 - Rendimiento: carga del calendario < 2 segundos.

 - Disponibilidad: 99% mensual.

## Prioridades
 - Alta: Agenda, registro/login, evitar doble reserva, notificaciones de confirmación.

 - Media: Cancelaciones y reagendamiento, bloqueo de tiempos por barbero.

 - Baja: Reportes avanzados, integración con calendario externo, pasarela de pago.

## Canales y plataformas
 - Versión inicial: Web responsive (celular y escritorio).

 - Acceso: clientes y staff vía navegador.

 - Futuro: apps móviles nativas (opcional).

## Plazo deseado
 - Primera versión funcional de la API en 4–6 semanas (MVP con agenda, usuarios y citas).

## Integraciones (futuro/MVP)
 - Email/WhatsApp para recordatorios.
