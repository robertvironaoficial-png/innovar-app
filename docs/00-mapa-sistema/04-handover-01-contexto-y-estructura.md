# Handover 01 — Contexto y estructura documental

## Objetivo actual del proyecto

El proyecto **Innovar App** está en una fase de **documentación integral**. El objetivo es que GitHub se convierta en la memoria funcional y técnica del sistema antes de tocar implementación, migraciones o cambios de base de datos.

## Regla operativa de esta fase

- No modificar Supabase.
- No crear migraciones.
- No alterar datos.
- No refactorizar código todavía.
- Sí consultar tablas, relaciones, columnas, comentarios y recursos existentes.
- Sí documentar el sistema de forma ordenada en GitHub.

## Repositorio oficial

- GitHub: `robertvironaoficial-png/innovar-app`
- Rama utilizada: `main`
- Permisos verificados: `admin`

## Proyecto Supabase

- Project ID: `xdzbjptozeqcbnaqhtye`
- Nombre observado: `Innovar CRM`

## Estructura documental principal creada

```text
docs/
  00-mapa-sistema/
  01-cotizaciones/
  02-operaciones/
  03-configuracion/
  04-base-de-datos/
```

## Documentos globales publicados

```text
docs/00-mapa-sistema/
  README.md
  01-matriz-modulos-y-tablas.md
  02-plan-de-trabajo-extraccion-supabase.md
  03-continuidad-proyecto.md
  04-handover-01-contexto-y-estructura.md
```

## Estructura de navegación visible del sistema

### Sidebar operativo

```text
Dashboard
Proyectos
Clientes & Ventas
  Directorio
  Solicitudes / Leads
  Cotizaciones
Agenda & Tareas
  Citas
  Tareas
Finanzas
  Pagos
  Gastos
  Cierres contables
```

### Hub de Configuración

```text
Catálogos Maestros
  Materiales e Insumos
  Tarifario y Precios
  Días Festivos

Accesos y Seguridad
  Usuarios y Roles
  Auditoría del Sistema
  Notificaciones WhatsApp
```

## Carpetas de Operaciones ya creadas

```text
docs/02-operaciones/
  dashboard/
  proyectos/
  clientes-y-ventas/
    directorio/
    solicitudes-leads/
  agenda-y-tareas/
    citas/
    tareas/
  finanzas/
    pagos/
    gastos/
    cierres-contables/
```

## Carpetas de Configuración ya creadas

```text
docs/03-configuracion/
  catalogos-maestros/
    materiales-e-insumos/
    tarifario-y-precios/
    dias-festivos/
  accesos-y-seguridad/
    usuarios-y-roles/
    auditoria-del-sistema/
    notificaciones-whatsapp/
```

## Módulo Cotizaciones ya trabajado

El módulo `docs/01-cotizaciones/` ya fue estructurado y cuenta con seis categorías comerciales normalizadas:

1. Cocinas Integrales.
2. Centro de TV.
3. Acabados Especiales.
4. Closets.
5. Mesones.
6. Puertas.

Cada categoría contiene al menos:

```text
README.md
00-fuente-de-verdad-normalizada.md
```

## Siguiente paso recomendado

Continuar con la documentación profunda de:

```text
docs/02-operaciones/proyectos/
```

Ese módulo fue priorizado porque conecta clientes, cotizaciones aprobadas, ejecución, diseño, instalación, finanzas, garantías y cierres.