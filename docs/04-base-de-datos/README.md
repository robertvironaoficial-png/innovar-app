# Base de Datos — Clasificación Global

## 1. Propósito

Esta carpeta documenta, en modo inventario y clasificación, la base de datos del sistema Innovar App.

En esta etapa no se modificará el esquema ni se ejecutarán cambios estructurales. El objetivo es comprender el sistema completo y relacionar sus tablas con los módulos visibles del producto.

---

# 2. Clasificación funcional preliminar de tablas

## 2.1 Identidad, acceso y seguridad

- `profiles`
- `audit_log`
- `audit_logs`

## 2.2 Clientes y ventas

- `clients`
- `quotations`
- `quotation_items`

## 2.3 Proyectos

- `projects`
- `project_photos`
- `warranties`
- `warranty_claims`
- `satisfaction_surveys`

## 2.4 Agenda y tareas

- `tasks`
- `availability_slots`
- `task_comments`
- `task_attachments`
- `calendar_sync_queue`

## 2.5 Finanzas

- `payments`
- `expenses`
- `accounting_closures`

## 2.6 Configuración y catálogos

- `materials`
- `pricing_catalog`
- `holidays`

## 2.7 Notificaciones y automatizaciones

- `notifications`
- `notification_queue`
- `whatsapp_message_log`
- `meta_whatsapp_status_events`
- `pdf_generation_queue`
- `scheduled_job_log`

## 2.8 Diccionarios internos del sistema

- `bucket_dictionary`
- `system_dictionary`

---

# 3. Relación preliminar con módulos del producto

| Dominio | Tablas principales |
| --- | --- |
| Usuarios y Roles | `profiles` |
| Auditoría del Sistema | `audit_log`, `audit_logs` |
| Directorio de Clientes | `clients` |
| Solicitudes / Leads | `clients` |
| Cotizaciones | `quotations`, `quotation_items`, `pdf_generation_queue` |
| Proyectos | `projects`, `project_photos`, `warranties`, `warranty_claims`, `satisfaction_surveys` |
| Citas | `tasks`, `availability_slots`, `calendar_sync_queue` |
| Tareas | `tasks`, `task_comments`, `task_attachments` |
| Pagos | `payments` |
| Gastos | `expenses` |
| Cierres contables | `accounting_closures` |
| Materiales e Insumos | `materials` |
| Tarifario y Precios | `pricing_catalog` |
| Días Festivos | `holidays` |
| Notificaciones WhatsApp | `notification_queue`, `whatsapp_message_log`, `meta_whatsapp_status_events` |

---

# 4. Observaciones globales iniciales

1. El sistema ya cuenta con dominios bien delimitados para ventas, proyectos, tareas, finanzas, seguridad y automatizaciones.
2. Hay tablas de diccionario interno que sugieren una intención de documentar infraestructura y procesos desde la propia base.
3. El módulo de cotizaciones está conectado a clientes, proyectos y generación de PDF.
4. El módulo de agenda parece compartir infraestructura con tareas y sincronización de calendario.
5. El sistema financiero se vincula con proyectos y clientes.

---

# 5. Riesgo de seguridad detectado durante el inventario

La tabla `public.scheduled_job_log` aparece con Row Level Security desactivado.

Esto no se corregirá en esta etapa, porque el trabajo actual es solo documental. Sin embargo, debe quedar registrado para futura revisión técnica y de seguridad.

SQL de referencia para una eventual remediación futura:

```sql
ALTER TABLE public.scheduled_job_log ENABLE ROW LEVEL SECURITY;
```

Antes de ejecutar esa medida deberán diseñarse y aprobarse las políticas de acceso correspondientes.

---

# 6. Próximos documentos recomendados

Después de cerrar el mapa global del sistema, esta carpeta podrá expandirse con:

- Inventario detallado de tablas.
- Relaciones entre dominios.
- Matriz tabla ↔ módulo.
- Diccionario funcional de entidades.
- Riesgos y deuda técnica detectada.
