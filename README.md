# Innovar App

Repositorio público de documentación, arquitectura funcional y evolución técnica del sistema **Innovar App**.

## Objetivo actual

La primera fase del repositorio está dedicada exclusivamente a **ordenar y documentar el sistema**, antes de trasladar o implementar código.

El trabajo se organizará por módulos de negocio, empezando por:

1. **Cotizaciones**
2. Resto de capacidades del sistema en fases posteriores

## Principio de trabajo

Durante esta etapa:

- No se modifica base de datos.
- No se implementa lógica nueva.
- No se migra código productivo.
- Se construye una documentación clara, auditable y escalable.
- Se define el plan técnico para separar correctamente frontend, backend y reglas de negocio.

## Estructura inicial del repositorio

```text
docs/
  01-cotizaciones/
    README.md
    00-plan-maestro.md
    01-taxonomia-categorias.md
    02-metodologia-documentacion.md
    cocinas-integrales/
      README.md
      00-fuente-de-verdad-normalizada.md
```

## Estado del proyecto

- Repositorio documental inicial: **creado**.
- Módulo activo: **Cotizaciones**.
- Primera categoría priorizada: **Cocinas Integrales**.
- Siguiente objetivo: cerrar la documentación funcional de Cocinas Integrales y convertirla en especificación de producto y backend.
