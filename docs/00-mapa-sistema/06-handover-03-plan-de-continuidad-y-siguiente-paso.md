# Handover 03 — Plan de continuidad y siguiente paso

## Propósito

Este documento indica exactamente cómo debe continuar la documentación del sistema después de la fase de organización global.

## Documento rector ya publicado

El plan completo de extracción desde Supabase está en:

```text
docs/00-mapa-sistema/02-plan-de-trabajo-extraccion-supabase.md
```

## Orden oficial de trabajo

### Fase A — Núcleo operativo

1. `docs/02-operaciones/proyectos/`
2. `docs/02-operaciones/clientes-y-ventas/directorio/`
3. `docs/02-operaciones/clientes-y-ventas/solicitudes-leads/`

### Fase B — Agenda y ejecución diaria

4. `docs/02-operaciones/agenda-y-tareas/tareas/`
5. `docs/02-operaciones/agenda-y-tareas/citas/`

### Fase C — Finanzas

6. `docs/02-operaciones/finanzas/pagos/`
7. `docs/02-operaciones/finanzas/gastos/`
8. `docs/02-operaciones/finanzas/cierres-contables/`

### Fase D — Configuración

9. `docs/03-configuracion/catalogos-maestros/materiales-e-insumos/`
10. `docs/03-configuracion/catalogos-maestros/tarifario-y-precios/`
11. `docs/03-configuracion/catalogos-maestros/dias-festivos/`

### Fase E — Seguridad y mensajería

12. `docs/03-configuracion/accesos-y-seguridad/usuarios-y-roles/`
13. `docs/03-configuracion/accesos-y-seguridad/auditoria-del-sistema/`
14. `docs/03-configuracion/accesos-y-seguridad/notificaciones-whatsapp/`

### Fase F — Visión ejecutiva

15. `docs/02-operaciones/dashboard/`

El Dashboard se documenta al final porque agrega datos de otros módulos.

---

# Paquete documental que debe producirse por módulo

Cada carpeta debe evolucionar hacia:

```text
README.md
01-proposito-y-alcance.md
02-tablas-y-entidades.md
03-relaciones-y-dependencias.md
04-flujos-funcionales.md
05-automatizaciones-y-eventos.md
06-riesgos-y-pendientes.md
```

## Contenido esperado

### `01-proposito-y-alcance.md`
- Qué representa el módulo.
- Qué problema de negocio resuelve.
- Qué parte de la UI corresponde a ese módulo.

### `02-tablas-y-entidades.md`
- Tablas principales.
- Columnas relevantes.
- Estados.
- Enums.
- Campos JSON.
- Comentarios técnicos existentes en Supabase.

### `03-relaciones-y-dependencias.md`
- Claves foráneas.
- Relaciones entrantes y salientes.
- Dependencias con otros módulos.

### `04-flujos-funcionales.md`
- Ciclo de vida del módulo.
- Estados operativos.
- Flujo de creación, actualización y cierre cuando aplique.

### `05-automatizaciones-y-eventos.md`
- Triggers.
- Funciones.
- Colas.
- Edge Functions.
- Logs o tablas de soporte.

### `06-riesgos-y-pendientes.md`
- Ambigüedades.
- Duplicidades.
- Inconsistencias.
- Dudas para negocio o ingeniería.
- Riesgos de seguridad o de diseño.

---

# Siguiente módulo exacto: Proyectos

La siguiente IA debe iniciar por:

```text
docs/02-operaciones/proyectos/
```

## Por qué Proyectos es prioritario

El módulo Proyectos conecta:

- Cliente.
- Cotización aprobada.
- Diseño.
- Producción.
- Instalación.
- Entrega.
- Finanzas.
- Garantías.
- Encuestas de satisfacción.
- Cierre contable.

## Tablas que debe estudiar para Proyectos

### Principales
- `projects`
- `project_photos`
- `warranties`
- `warranty_claims`
- `satisfaction_surveys`

### Relacionadas
- `clients`
- `quotations`
- `profiles`
- `tasks`
- `payments`
- `expenses`
- `accounting_closures`

## Temas que deben documentarse en Proyectos

1. Propósito del módulo.
2. Ciclo de vida de `projects.status`.
3. Relación con `approved_quotation_id`.
4. Relación con `client_id`.
5. Rol de `designer_id` y `created_by`.
6. Diseño, archivos y mediciones.
7. Fechas de diseño e instalación.
8. Campos de aprobación del cliente.
9. Archivado y salto de proceso de diseño.
10. Origen de datos mediante `data_origin`.
11. Relación con cierre contable.
12. Fotos del proyecto por etapa.
13. Garantías y reclamos.
14. Encuestas de satisfacción.
15. Cruce con tareas, pagos y gastos.

---

# Regla metodológica para la siguiente IA

La documentación debe clasificar cada afirmación como una de estas posibilidades:

- Hecho observado en Supabase.
- Inferencia técnica razonable.
- Decisión pendiente de validar.

No se deben presentar inferencias como hechos.

---

# Criterio de cierre del módulo Proyectos

Proyectos se considerará documentado en esta fase cuando:

1. Existan los seis documentos estándar de la carpeta.
2. Se hayan mapeado tablas, columnas y relaciones.
3. Se haya descrito el flujo funcional probable.
4. Se hayan registrado automatizaciones visibles o pendientes de revisar.
5. Se hayan documentado riesgos y dudas.
