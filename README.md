# 🚗 Arka01 — Plataforma de movilidad

> **Tu círculo. Tus viajes. Tu decisión.**
> Plataforma de movilidad que conecta pasajeros, conductores y cooperativas. Arka01 **no asigna conductores, solo los conecta**: cada pasajero construye su propia red de conductores de confianza, y los conductores se quedan con el **100 % de lo que cobran**, sin comisiones por viaje.

🌐 **Sitio:** [arka01.com](https://arka01.com)
👤 **Autor:** Gregorio Osorio — Desarrollador Full Stack (arquitectura, backend, frontend e integraciones)

> 🔒 El código fuente de este proyecto es **privado**. Este repositorio es una vitrina técnica: muestra qué hace la plataforma, cómo está construida y mi rol en ella. Si eres reclutador y quieres ver el código en detalle, escríbeme y coordinamos una revisión guiada.

---

## 📸 Capturas

![Cómo funciona](docs/img/como-funciona.jpg)

![Una plataforma para todos](docs/img/plataforma-para-todos.jpg)

🎥 **Video demo:** _(enlace a YouTube / Loom)_

---

## 💡 El modelo: confianza y cero comisiones

| Para quién | Propuesta |
|---|---|
| **Pasajeros** | Viajan con quienes confían y ven la tarifa exacta antes de aceptar. Guardan a los conductores que les gustaron en su flota para volver a pedirlos. |
| **Conductores** | Cero comisiones: se quedan con el 100 % de lo que cobran. Definen su tarifa y su horario, revisan la reputación del cliente antes de aceptar y forman su propia clientela. |
| **Cooperativas** | Gestionan su flota con un plan fijo, sin descuentos por carrera. |
| **Coordinadores** | Supervisan cada carrera en tiempo real desde un solo panel. |

**Cómo funciona:** 1) Creas tu cuenta → 2) Construyes tu flota de confianza (conductores que conoces o nuevos de tu zona) → 3) Pides la carrera directamente a quien elijas.

---

## ✨ Funcionalidades principales

### Para pasajeros
- Solicitud de viajes con **múltiples paradas** y rutas guardadas.
- **Negociación de tarifa**: el pasajero propone un precio y los conductores responden con ofertas.
- Chat en tiempo real con el conductor durante el viaje.
- **Seguimiento público del viaje**: un enlace para que familiares vean el recorrido en vivo.
- **Botón SOS**, contactos de confianza y **círculo de confianza**.
- Calificaciones y reseñas con motivos.
- Solicitud de viajes también desde **WhatsApp**, incluida la selección de ubicación.

### Para conductores
- Perfil público con **índice de confianza**, estadísticas y niveles (*tiers*) según su desempeño.
- Trabajo independiente, dentro de una cooperativa, o ambos.
- Planes de suscripción con cupones y promociones, en lugar de comisiones abusivas por viaje.
- Gestión de **flotas** (dueños con varios vehículos e invitación de conductores).
- Integración con **cooperativas de transporte**: membresías, asignación de viajes, billetera y cuentas bancarias.
- Canales de radio internos para comunicación entre conductores.
- Programa de referidos.

### Servicios adicionales
- **Express**: rutas compartidas con acompañantes, solicitudes e incidencias.
- **Viajes en van** interprovinciales con reservas y fotos del vehículo.

### Administración
- Panel administrativo con auditoría de acciones, configuración de tarifas, banners, FAQ, encuestas y soporte por tickets.
- **Chatbot** configurable con intenciones, palabras clave y registro de mensajes no reconocidos para mejorarlo.

---

## 🛠️ Stack técnico

| Capa | Tecnologías |
|---|---|
| Backend | PHP · Laravel · API REST versionada (`/api/v1`) |
| Frontend | Vue 3 · Tailwind CSS |
| Base de datos | MySQL |
| Tiempo real | Eventos / broadcasting, notificaciones push web |
| Integraciones | WhatsApp (webhooks), mapas y cálculo de rutas, pagos |
| Calidad | Pruebas automatizadas, Laravel Pint |

---

## 🏗️ Arquitectura (resumen)

```
 Pasajero (web/PWA) ─┐                 ┌─ Panel admin
 Conductor (web/PWA) ┼──► API Laravel ─┼─ Cooperativas / Flotas
 WhatsApp ───────────┘   (v1, auth)    └─ Chatbot
                             │
                ┌────────────┼────────────┐
              MySQL     Colas/Jobs   Broadcasting + Push
```

- Más de **60 modelos de dominio** organizados por contexto: viajes, conductores, cooperativas, suscripciones, seguridad, soporte.
- Roles separados: pasajero, conductor, cooperativa, dueño de flota y administrador.
- Registro de auditoría y eventos del sistema para trazabilidad.

---

## 👨‍💻 Mi rol

Diseñé y desarrollé la plataforma de punta a punta:
- Modelado del dominio y de la base de datos.
- Desarrollo del backend, la API y el frontend.
- Integración con WhatsApp, mapas y notificaciones.
- Despliegue y mantenimiento.

---

## 📬 Contacto

- LinkedIn: [in/gregorio-osorio](https://www.linkedin.com/in/gregorio-osorio)
- Web: [siglotecnologico.com](https://siglotecnologico.com)

---

© Gregorio Osorio. Todos los derechos reservados. Ver [LICENSE](LICENSE).
