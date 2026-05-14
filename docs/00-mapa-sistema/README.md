# Mapa Global del Sistema — Innovar App

## 1. Propósito

Esta carpeta documenta el mapa general del sistema Innovar App antes de iniciar cualquier migración técnica o implementación.

El objetivo es clasificar el sistema desde tres perspectivas:

1. Módulos visibles en el sidebar operativo.
2. Módulos visibles en el Hub de Configuración.
3. Tablas y recursos existentes en la base de datos.

Esta etapa es documental. No implica modificación de base de datos ni cambios de código.

---

# 2. Estructura documental global

```text
docs/
  00-mapa-sistema/
  01-cotizaciones/
  02-operaciones/
  03-configuracion/
  04-base-de-datos/
```

## 2.1 Mapa del sistema

Contiene la clasificación general del producto y la relación entre interfaz, módulos y base de datos.

## 2.2 Cotizaciones

Contiene la documentación funcional de las categorías comerciales de cotización.

## 2.3 Operaciones

Agrupa los módulos visibles en el sidebar principal del sistema.

## 2.4 Configuración

Agrupa los módulos visibles en el Hub de Configuración.

## 2.5 Base de datos

Contiene inventarios, clasificación de tablas, relaciones y dependencias del sistema.

---

# 3. Módulos visibles del sidebar operativo

Según la vista principal del sistema, el sidebar operativo se organiza así:

1. Dashboard.
2. Proyectos.
3. Clientes y Ventas.
   - Directorio.
   - Solicitudes / Leads.
   - Cotizaciones.
4. Agenda y Tareas.
   - Citas.
   - Tareas.
5. Finanzas.
   - Pagos.
   - Gastos.
   - Cierres contables.

---

# 4. Módulos visibles del Hub de Configuración

Según la vista del Hub de Configuración, el sistema administrativo se organiza así:

## 4.1 Catálogos Maestros

- Materiales e Insumos.
- Tarifario y Precios.
- Días Festivos.

## 4.2 Accesos y Seguridad

- Usuarios y Roles.
- Auditoría del Sistema.
- Notificaciones WhatsApp.

---

# 5. Principio de clasificación

Cada módulo del sistema deberá documentarse siguiendo este patrón:

1. Propósito funcional.
2. Pantallas o vistas relacionadas.
3. Tablas principales.
4. Tablas auxiliares.
5. Flujos principales.
6. Reglas de negocio.
7. Automatizaciones relacionadas.
8. Riesgos o decisiones pendientes.

---

# 6. Estado actual

Ya se inició la documentación del módulo **Cotizaciones** y sus categorías comerciales.

A partir de esta etapa se inicia la clasificación global del resto del sistema para posteriormente documentar módulo por módulo.
