# Plan de Trabajo — Extracción y Documentación del Sistema desde Supabase

## 1. Propósito

Este documento define el plan ordenado para trasladar el conocimiento técnico y funcional existente en Supabase hacia la documentación del repositorio GitHub de **Innovar App**.

El objetivo no es modificar la base de datos ni implementar código en esta etapa. El objetivo es:

- Entender el sistema completo.
- Clasificar sus módulos funcionales.
- Relacionar cada carpeta de GitHub con las tablas y recursos que la soportan.
- Documentar la estructura real del producto de forma profesional.
- Preparar una futura etapa de arquitectura, refactor y migración controlada.

---

# 2. Principios de trabajo

## 2.1 Modo lectura y análisis

Durante esta fase:

- No se modificará la base de datos.
- No se crearán migraciones.
- No se cambiarán políticas, triggers ni funciones.
- No se alterarán datos productivos.
- Solo se consultará, clasificará y documentará.

## 2.2 Documentación antes que implementación

Antes de proponer cambios técnicos, cada área del sistema deberá quedar suficientemente descrita:

- Qué hace.
- Qué tablas usa.
- Qué relaciones tiene.
- Qué reglas parecen existir.
- Qué automatizaciones la rodean.
- Qué dudas o riesgos presenta.

## 2.3 Organización por carpetas funcionales

La documentación se desarrollará usando la estructura ya creada en GitHub:

```text
docs/
  00-mapa-sistema/
  01-cotizaciones/
  02-operaciones/
  03-configuracion/
  04-base-de-datos/
```

La información extraída desde Supabase se llevará siempre a la carpeta funcional correspondiente.

---

# 3. Objetivo de la fase actual

La fase actual consiste en construir una **documentación institucional completa del sistema existente**, partiendo de Supabase y del producto visible.

## Resultado esperado

Al terminar esta fase deberíamos tener:

1. Todos los módulos visibles del sistema documentados.
2. Todas las tablas de Supabase clasificadas por dominio.
3. Cada tabla relacionada con una o más carpetas funcionales.
4. Cada flujo importante identificado.
5. Automatizaciones, colas, diccionarios y seguridad registrados.
6. Riesgos, inconsistencias y deuda técnica visibles para la siguiente fase.

---

# 4. Método general de extracción por carpeta

Cada carpeta funcional se trabajará siguiendo el mismo proceso.

## Paso 1 — Identificar el módulo funcional

Se toma una carpeta del repositorio, por ejemplo:

```text
02-operaciones/proyectos/
```

Y se responde:

- ¿Qué parte del producto representa?
- ¿Qué usuario la utiliza?
- ¿Qué problema de negocio resuelve?

## Paso 2 — Identificar tablas principales

Se revisa Supabase para detectar:

- Tablas directamente asociadas.
- Tablas dependientes.
- Relaciones mediante claves foráneas.
- Tablas de soporte o auxiliares.

## Paso 3 — Levantar la estructura técnica

Para cada tabla asociada se documenta:

- Nombre.
- Propósito.
- Número de filas actual, solo como señal de uso.
- Columnas relevantes.
- Tipos de dato importantes.
- Enumeraciones.
- Restricciones.
- Llaves primarias.
- Relaciones entrantes y salientes.
- Comentarios técnicos existentes.

## Paso 4 — Interpretar la lógica funcional

A partir del modelo de datos se documenta:

- Qué entidades de negocio existen.
- Qué estados maneja el sistema.
- Qué flujo parece soportar.
- Qué eventos pueden generar cambios.
- Qué información se conserva como histórico o snapshot.

## Paso 5 — Detectar automatizaciones o dependencias

Se revisa si el módulo toca:

- Triggers.
- Funciones de base de datos.
- Edge Functions.
- Colas.
- Logs.
- Diccionarios internos.
- Integraciones externas.

## Paso 6 — Registrar dudas, riesgos y hallazgos

Cada módulo debe dejar visibles:

- Ambigüedades funcionales.
- Tablas duplicadas o parecidas.
- Campos potencialmente solapados.
- Decisiones arquitectónicas pendientes.
- Riesgos de seguridad o coherencia.

## Paso 7 — Publicar documentación en GitHub

Una vez revisado el módulo, se documenta dentro de su carpeta con archivos Markdown estandarizados.

---

# 5. Paquete documental estándar por carpeta

Cada módulo o submódulo deberá evolucionar hacia una estructura como esta:

```text
README.md
01-proposito-y-alcance.md
02-tablas-y-entidades.md
03-relaciones-y-dependencias.md
04-flujos-funcionales.md
05-automatizaciones-y-eventos.md
06-riesgos-y-pendientes.md
```

## 5.1 README.md

Resumen ejecutivo del módulo.

## 5.2 Propósito y alcance

Explica la función de negocio del módulo.

## 5.3 Tablas y entidades

Relaciona el módulo con las tablas de Supabase.

## 5.4 Relaciones y dependencias

Describe conexiones con otros módulos y entidades.

## 5.5 Flujos funcionales

Documenta procesos soportados por el módulo.

## 5.6 Automatizaciones y eventos

Registra triggers, colas, notificaciones y funciones relacionadas.

## 5.7 Riesgos y pendientes

Consolida temas que requieren validación antes de implementar mejoras.

---

# 6. Orden propuesto de documentación

El orden no será aleatorio. Se prioriza por centralidad del negocio y capacidad de explicar el resto del sistema.

## Fase A — Núcleo operativo del negocio

### A1. Proyectos

Ruta:

```text
02-operaciones/proyectos/
```

Motivo de prioridad:

- Conecta clientes, cotizaciones aprobadas, tareas, diseño, producción, instalación, pagos, gastos y cierre contable.
- Es uno de los ejes principales de la operación.

### A2. Clientes y Ventas — Directorio

Ruta:

```text
02-operaciones/clientes-y-ventas/directorio/
```

Motivo:

- `clients` es una entidad transversal.
- Sirve de base para leads, cotizaciones, proyectos, pagos y garantías.

### A3. Clientes y Ventas — Solicitudes / Leads

Ruta:

```text
02-operaciones/clientes-y-ventas/solicitudes-leads/
```

Motivo:

- Ayuda a explicar la etapa previa a cliente consolidado y proyecto.
- Existen campos de scoring, urgencia, asignación y conversión.

## Fase B — Agenda y ejecución diaria

### B1. Tareas

Ruta:

```text
02-operaciones/agenda-y-tareas/tareas/
```

### B2. Citas

Ruta:

```text
02-operaciones/agenda-y-tareas/citas/
```

Motivo:

- Tareas y citas parecen compartir infraestructura.
- Se apoyan en disponibilidad, comentarios, adjuntos y sincronización de calendario.

## Fase C — Finanzas

### C1. Pagos

Ruta:

```text
02-operaciones/finanzas/pagos/
```

### C2. Gastos

Ruta:

```text
02-operaciones/finanzas/gastos/
```

### C3. Cierres contables

Ruta:

```text
02-operaciones/finanzas/cierres-contables/
```

Motivo:

- Permiten comprender el control financiero del proyecto.
- Se relacionan con proyectos, clientes y responsables internos.

## Fase D — Configuración y catálogos

### D1. Materiales e Insumos

Ruta:

```text
03-configuracion/catalogos-maestros/materiales-e-insumos/
```

### D2. Tarifario y Precios

Ruta:

```text
03-configuracion/catalogos-maestros/tarifario-y-precios/
```

### D3. Días Festivos

Ruta:

```text
03-configuracion/catalogos-maestros/dias-festivos/
```

Motivo:

- Estos módulos alimentan reglas operativas y comerciales.

## Fase E — Seguridad, auditoría y mensajería

### E1. Usuarios y Roles

Ruta:

```text
03-configuracion/accesos-y-seguridad/usuarios-y-roles/
```

### E2. Auditoría del Sistema

Ruta:

```text
03-configuracion/accesos-y-seguridad/auditoria-del-sistema/
```

### E3. Notificaciones WhatsApp

Ruta:

```text
03-configuracion/accesos-y-seguridad/notificaciones-whatsapp/
```

Motivo:

- Documentan gobierno, trazabilidad y automatizaciones.

## Fase F — Dashboard y visión ejecutiva

### F1. Dashboard

Ruta:

```text
02-operaciones/dashboard/
```

Motivo de dejarlo después:

- El Dashboard es una capa agregadora.
- Conviene documentarlo cuando ya estén claros los módulos que alimentan sus métricas.

---

# 7. Tratamiento específico de Cotizaciones

El módulo de **Cotizaciones** ya cuenta con una carpeta especializada:

```text
01-cotizaciones/
```

Y con sus seis categorías comerciales documentadas a nivel funcional:

1. Cocinas Integrales.
2. Centro de TV.
3. Acabados Especiales.
4. Closets.
5. Mesones.
6. Puertas.

## Próximo nivel de trabajo para Cotizaciones

Cuando llegue el momento de retomar este módulo desde Supabase, se documentará:

- Tablas `quotations` y `quotation_items`.
- Relaciones con `clients`, `projects` y generación de PDF.
- Estados, versiones e historial.
- Diferencia entre lógica comercial documentada y estructura técnica actual.
- Riesgos de divergencia entre frontend, backend y base de datos.

---

# 8. Inventario técnico transversal a documentar en paralelo

Además de las carpetas funcionales, se mantendrá una documentación transversal en:

```text
04-base-de-datos/
```

## Documentos futuros sugeridos

```text
01-inventario-tablas.md
02-relaciones-globales.md
03-enums-y-estados.md
04-colas-y-automatizaciones.md
05-seguridad-y-rls.md
06-diccionario-de-entidades.md
```

---

# 9. Forma de trabajo durante cada sesión

Cada sesión de documentación seguirá este ritmo:

## 1. Elegimos una carpeta

Ejemplo:

```text
Proyectos
```

## 2. Revisamos Supabase solo en lectura

- Tablas.
- Campos.
- Relaciones.
- Enums.
- Comentarios.
- Recursos asociados.

## 3. Sintetizamos el módulo

- Qué representa.
- Cómo se usa.
- Qué cruces tiene con el resto del sistema.

## 4. Publicamos documentación en GitHub

Se crean o actualizan los Markdown correspondientes.

## 5. Cerramos con hallazgos

Cada carpeta termina con:

- Estado de documentación.
- Riesgos.
- Dudas.
- Siguiente paso.

---

# 10. Criterios de calidad

La documentación debe ser:

- Precisa.
- Comprensible para negocio y tecnología.
- Reutilizable.
- Coherente con el sistema real.
- Trazable hacia Supabase.
- Útil para una futura implementación o refactor.

No se deben asumir reglas no visibles en la base o en la documentación del cliente. Cuando algo sea una inferencia, debe indicarse como tal.

---

# 11. Riesgos conocidos al iniciar la fase

Durante la primera lectura global del sistema ya se detectaron temas que deberán estudiarse más adelante:

1. `scheduled_job_log` aparece con RLS desactivado.
2. Existen dos tablas de auditoría: `audit_log` y `audit_logs`.
3. `clients` parece cumplir funciones tanto de cliente como de lead.
4. `tasks` parece soportar tareas y también citas.
5. El módulo de cotizaciones debe contrastarse cuidadosamente con la documentación funcional ya consolidada.

Estos puntos no se resolverán aún; quedarán documentados en los módulos correspondientes.

---

# 12. Decisión de inicio recomendada

La primera carpeta a desarrollar debe ser:

```text
02-operaciones/proyectos/
```

## Razón

Es el módulo que mejor explica el sistema completo porque conecta:

- Cliente.
- Cotización aprobada.
- Flujo operativo.
- Diseño.
- Producción.
- Instalación.
- Entrega.
- Finanzas.
- Cierre contable.

Una vez documentado Proyectos, el resto del sistema será más sencillo de ordenar.
