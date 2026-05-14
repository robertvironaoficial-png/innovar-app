# Handover 04 — Riesgos, hallazgos y reglas de continuidad

## Propósito

Este documento resume los hallazgos críticos detectados durante la organización del sistema y define las reglas que debe respetar la siguiente IA para continuar correctamente.

---

# 1. Hallazgos técnicos y funcionales ya detectados

## 1.1 Cotizaciones sin ítems detallados

Durante la revisión inicial se observaron registros en:

- `quotations`

pero no se encontraron registros en:

- `quotation_items`

Esto debe investigarse cuando se retome el módulo de Cotizaciones, porque la arquitectura deseada requiere que las cotizaciones tengan detalle de ítems y configuración.

---

## 1.2 Clientes y leads parecen compartir tabla

La tabla:

- `clients`

contiene campos de cliente consolidado y campos propios de gestión comercial de leads:

- `status`
- `urgency`
- `assigned_to`
- `assigned_at`
- `converted_to_id`
- `lead_score`
- `lead_score_details`
- `lead_scored_at`

La siguiente IA debe analizar si:

- Directorio y Solicitudes / Leads son dos vistas del mismo modelo.
- Existe un flujo de conversión interno en la misma tabla.
- Se requiere una futura separación conceptual o basta con documentar la entidad única.

---

## 1.3 Tareas y citas parecen compartir infraestructura

La tabla:

- `tasks`

incluye campos que sugieren uso tanto para tareas operativas como para citas:

- `appointment_type`
- `time_slot`
- `task_category`

Además, existe la categoría:

- `cita`

La siguiente IA debe estudiar cuidadosamente la relación entre:

- `tasks`
- `availability_slots`
- `calendar_sync_queue`

---

## 1.4 Duplicidad potencial en auditoría

Existen dos tablas diferentes:

- `audit_log`
- `audit_logs`

Con esquemas distintos. Se debe investigar si:

- Una es legada.
- Una corresponde a una versión antigua o frontend.
- Ambas cumplen funciones distintas.
- Existe duplicidad que debería documentarse como deuda técnica.

---

## 1.5 Riesgo de seguridad detectado

La tabla:

- `scheduled_job_log`

aparece con Row Level Security desactivado.

Este hallazgo debe mantenerse documentado, pero no debe corregirse en esta fase.

SQL de referencia futura:

```sql
ALTER TABLE public.scheduled_job_log ENABLE ROW LEVEL SECURITY;
```

Antes de ejecutarlo deben diseñarse políticas de acceso.

---

# 2. Hallazgos pendientes por módulo comercial de Cotizaciones

## 2.1 Cocinas Integrales

- Definir si los módulos especiales tienen precio adicional o están incluidos.
- Formalizar las fórmulas exactas de isla y barra.
- Confirmar tratamiento de IVA o impuestos.
- Separar definitivamente qué queda en Cocinas, qué pasa a Acabados y qué pasa a Puertas.

## 2.2 Centro de TV

- Resolver LED fijo de `$250.000` vs LED por metro lineal.
- Resolver alto brillo fijo vs alto brillo calculado por piezas.
- Confirmar regla de descuento cuando hay 0 o 1 repisa.
- Definir si el ancho solo acepta valores discretos.

## 2.3 Acabados Especiales

- Confirmar si es categoría autónoma o complemento exclusivo de cocinas.
- Confirmar si las bisagras son pares totales o adicionales.
- Definir política de redondeo.

## 2.4 Closets

- Confirmar si profundidad correcta es `0.60 m` y `0.45 m`.
- Definir si notas como “sin zapatero” afectan precio.
- Confirmar si accesorios base pueden variar sin recargo.

## 2.5 Mesones

- Revisar inconsistencia matemática en caso mixto de isla de cuarzo.
- Confirmar si el nombre final del módulo es Mesones o Mesones con Granito.
- Validar si transporte se cobra una vez por cotización o por bloque de mesones.

## 2.6 Puertas

- Aclarar el límite exacto de 85 cm.
- Confirmar si altura afecta precio.
- Confirmar si dintel y color de herrajes son siempre informativos.

---

# 3. Reglas metodológicas obligatorias para la continuidad

La siguiente IA debe trabajar con estas reglas:

1. No modificar Supabase durante esta etapa.
2. No crear código de implementación.
3. No asumir reglas que no estén sustentadas.
4. Separar claramente:
   - Hecho observado.
   - Inferencia técnica.
   - Decisión pendiente.
5. Documentar cada módulo directamente en GitHub.
6. Mantener la estructura de carpetas ya creada.
7. Seguir el orden definido en el plan de trabajo.

---

# 4. Próximo módulo obligatorio

El siguiente módulo a documentar es:

```text
docs/02-operaciones/proyectos/
```

Debe estudiarse desde Supabase usando al menos:

- `projects`
- `project_photos`
- `warranties`
- `warranty_claims`
- `satisfaction_surveys`

Y cruzarse con:

- `clients`
- `quotations`
- `profiles`
- `tasks`
- `payments`
- `expenses`
- `accounting_closures`

---

# 5. Documentos que deben crearse para Proyectos

```text
01-proposito-y-alcance.md
02-tablas-y-entidades.md
03-relaciones-y-dependencias.md
04-flujos-funcionales.md
05-automatizaciones-y-eventos.md
06-riesgos-y-pendientes.md
```

---

# 6. Criterio de calidad

La documentación futura debe ser:

- Clara.
- Técnica cuando corresponda.
- Entendible para negocio.
- Coherente con el modelo de datos real.
- Útil para una futura migración, refactor o rediseño.

La meta no es escribir mucho; la meta es dejar el sistema entendible y operable para cualquier persona o IA que retome el trabajo.
