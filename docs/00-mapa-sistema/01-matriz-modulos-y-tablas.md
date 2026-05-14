# Matriz Global — Módulos del Sistema y Tablas Relacionadas

## 1. Propósito

Este documento conecta la estructura visible de Innovar App con el inventario actual de la base de datos.

Su finalidad es servir como puente documental entre:

- La navegación funcional del producto.
- Los dominios de negocio.
- Las entidades y tablas existentes.

Esta clasificación es preliminar y será refinada cuando se documente cada carpeta en profundidad.

---

# 2. Sidebar operativo

## 2.1 Dashboard

### Dominio funcional

Vista ejecutiva de indicadores, accesos rápidos y métricas operativas.

### Tablas potencialmente relacionadas

- `clients`
- `projects`
- `quotations`
- `tasks`
- `payments`
- `expenses`
- `notifications`

### Comentario

El Dashboard probablemente no representa una entidad propia, sino una capa de agregación transversal de datos.

---

## 2.2 Proyectos

### Dominio funcional

Gestión de proyectos aprobados y de su ciclo de vida operativo.

### Tablas principales

- `projects`

### Tablas auxiliares

- `project_photos`
- `tasks`
- `payments`
- `expenses`
- `warranties`
- `warranty_claims`
- `satisfaction_surveys`

### Relaciones relevantes

- Proyecto ↔ Cliente.
- Proyecto ↔ Cotización aprobada.
- Proyecto ↔ Responsable de diseño.
- Proyecto ↔ Pagos, gastos y cierre contable.

---

## 2.3 Clientes y Ventas — Directorio

### Dominio funcional

Gestión de clientes finales.

### Tablas principales

- `clients`

### Tablas relacionadas

- `quotations`
- `projects`
- `payments`
- `expenses`
- `warranties`
- `satisfaction_surveys`

---

## 2.4 Clientes y Ventas — Solicitudes / Leads

### Dominio funcional

Gestión comercial de prospectos, priorización y asignación.

### Tablas principales

- `clients`

### Campos relevantes observados

- `status`
- `urgency`
- `assigned_to`
- `assigned_at`
- `converted_to_id`
- `lead_score`
- `lead_score_details`
- `lead_scored_at`

### Comentario

La tabla `clients` actualmente parece absorber tanto clientes consolidados como solicitudes/leads.

---

## 2.5 Clientes y Ventas — Cotizaciones

### Dominio funcional

Generación y gestión de propuestas económicas.

### Tablas principales

- `quotations`
- `quotation_items`

### Tablas relacionadas

- `clients`
- `projects`
- `pdf_generation_queue`

### Comentario

Este módulo ya cuenta con documentación especializada en `docs/01-cotizaciones/`.

---

## 2.6 Agenda y Tareas — Citas

### Dominio funcional

Gestión de citas, disponibilidad y sincronización de agenda.

### Tablas principales

- `tasks`
- `availability_slots`

### Tablas auxiliares

- `calendar_sync_queue`

### Comentario

Las citas parecen modelarse como una variante de `tasks`, apoyadas por disponibilidad y sincronización externa.

---

## 2.7 Agenda y Tareas — Tareas

### Dominio funcional

Seguimiento operativo de pendientes, estados y responsables.

### Tablas principales

- `tasks`

### Tablas auxiliares

- `task_comments`
- `task_attachments`
- `notifications`

---

## 2.8 Finanzas — Pagos

### Dominio funcional

Registro de ingresos asociados a proyectos o clientes.

### Tablas principales

- `payments`

### Tablas relacionadas

- `projects`
- `clients`
- `profiles`

---

## 2.9 Finanzas — Gastos

### Dominio funcional

Registro de egresos y aprobación de gastos.

### Tablas principales

- `expenses`

### Tablas relacionadas

- `projects`
- `clients`
- `profiles`

---

## 2.10 Finanzas — Cierres contables

### Dominio funcional

Cierre económico y consolidación financiera por proyecto.

### Tablas principales

- `accounting_closures`

### Tablas relacionadas

- `projects`
- `profiles`

---

# 3. Hub de Configuración

## 3.1 Materiales e Insumos

### Dominio funcional

Catálogo de recursos, materiales, herrajes y acabados.

### Tablas principales

- `materials`

---

## 3.2 Tarifario y Precios

### Dominio funcional

Catálogo de tarifas y valores de referencia.

### Tablas principales

- `pricing_catalog`

---

## 3.3 Días Festivos

### Dominio funcional

Calendario de excepciones laborales y días no hábiles.

### Tablas principales

- `holidays`

---

## 3.4 Usuarios y Roles

### Dominio funcional

Gestión de identidad interna y niveles de acceso.

### Tablas principales

- `profiles`

---

## 3.5 Auditoría del Sistema

### Dominio funcional

Trazabilidad de acciones críticas y cambios.

### Tablas principales

- `audit_log`
- `audit_logs`

### Comentario

Existen dos tablas de auditoría con modelos distintos. Este punto deberá estudiarse al documentar el módulo.

---

## 3.6 Notificaciones WhatsApp

### Dominio funcional

Mensajería automatizada, colas de envío y trazabilidad de estados.

### Tablas principales

- `notification_queue`
- `whatsapp_message_log`
- `meta_whatsapp_status_events`

### Tablas relacionadas

- `notifications`
- `scheduled_job_log`

---

# 4. Recursos transversales

## 4.1 Notificaciones internas

- `notifications`

## 4.2 Colas y automatizaciones

- `pdf_generation_queue`
- `calendar_sync_queue`
- `scheduled_job_log`

## 4.3 Diccionarios internos del sistema

- `bucket_dictionary`
- `system_dictionary`

---

# 5. Lecturas preliminares del sistema

1. El producto está organizado alrededor de cinco macrodominios:
   - Comercial.
   - Proyectos.
   - Agenda operativa.
   - Finanzas.
   - Configuración y seguridad.

2. Varias entidades sirven a más de un módulo:
   - `clients` participa en directorio, leads, cotizaciones, pagos y garantías.
   - `projects` conecta ventas, operación y finanzas.
   - `tasks` conecta tareas y citas.

3. Existen capacidades transversales ya representadas en base de datos:
   - Auditoría.
   - Notificaciones.
   - Automatizaciones.
   - Sincronización de calendario.
   - Cola de PDF.

---

# 6. Siguiente paso recomendado

Después de esta matriz global, el proyecto puede avanzar de manera ordenada en una de dos direcciones:

1. Documentar **Operaciones** carpeta por carpeta empezando por `Dashboard` o `Proyectos`.
2. Documentar **Configuración** carpeta por carpeta empezando por `Materiales e Insumos` o `Usuarios y Roles`.

La recomendación funcional es iniciar por **Operaciones → Proyectos**, porque este módulo conecta ventas, ejecución y finanzas.
