# Plan Maestro de Documentación — Sistema de Cotizaciones

## 1. Propósito

Este documento define el plan de trabajo general para documentar el sistema de **Cotizaciones** de Innovar App de forma ordenada, progresiva y orientada a una futura implementación robusta.

La documentación será el punto de partida para:

- Entender el negocio sin ambigüedades.
- Separar adecuadamente interfaz, reglas de negocio y motor de cálculo.
- Reducir fallos por lógica distribuida.
- Preparar un traslado técnico futuro hacia una arquitectura mantenible.

---

# 2. Alcance de esta fase

Durante esta etapa el equipo trabajará únicamente en:

- Levantamiento de información.
- Organización documental.
- Normalización de reglas de negocio.
- Identificación de inconsistencias.
- Definición de estructuras futuras.
- Planeación funcional y técnica.

## Fuera de alcance por ahora

- Cambios en base de datos.
- Creación de migraciones.
- Programación de backend.
- Refactor del frontend.
- Automatizaciones productivas.
- Publicación de contratos definitivos de API.

---

# 3. Estrategia global

La documentación se construirá en cuatro niveles:

## Nivel 1 — Módulo

Se documenta el dominio de negocio completo, en este caso:

- Cotizaciones.

## Nivel 2 — Categoría

Cada categoría comercial se documenta de manera independiente.

Categorías iniciales:

1. Cocinas Integrales.
2. Acabados Especiales.
3. Centro de TV.
4. Closets.
5. Puertas.
6. Mesones con Granito.

## Nivel 3 — Regla de negocio

Cada categoría se descompone en:

- Conceptos.
- Parámetros.
- Fórmulas.
- Excepciones.
- Validaciones.
- Casos de ejemplo.

## Nivel 4 — Traducción futura a software

Una vez consolidada la categoría, se documentará:

- Qué debe enviar el frontend.
- Qué debe calcular el backend.
- Qué debe persistirse.
- Qué debe auditarse.
- Qué respuestas y errores deberían existir.

---

# 4. Orden de ejecución

## Fase 1 — Fundaciones del módulo Cotizaciones

Objetivo: crear una base documental profesional y común para todo el dominio.

Entregables:

- README general del repositorio.
- README del módulo Cotizaciones.
- Plan maestro.
- Taxonomía de categorías.
- Metodología documental.

## Fase 2 — Categoría 1: Cocinas Integrales

Objetivo: convertir la documentación comercial del cliente en una especificación funcional completa y utilizable para ingeniería.

Entregables esperados:

1. Fuente de verdad normalizada.
2. Glosario de términos.
3. Reglas funcionales.
4. Modelo de entradas.
5. Modelo de cálculo.
6. Casos y ejemplos.
7. Validaciones.
8. Preguntas abiertas.
9. Riesgos de implementación.
10. Propuesta inicial de desacople frontend-backend.

## Fase 3 — Resto de categorías

Una vez cerrada Cocinas Integrales, se repetirá la metodología para:

- Acabados Especiales.
- Centro de TV.
- Closets.
- Puertas.
- Mesones con Granito.

## Fase 4 — Consolidación transversal del motor de cotización

Con las seis categorías documentadas se construirá una visión sistémica:

- Reglas compartidas.
- Diferencias entre categorías.
- Catálogo de parámetros reutilizables.
- Patrón general del motor de cálculo.
- Estrategia de persistencia.
- Diseño futuro de contratos de servicio.

## Fase 5 — Planeación técnica de implementación

Solo después de cerrar la documentación funcional, se preparará:

- Plan de migración técnica.
- Estrategia de backend.
- Estrategia de frontend.
- Matriz de riesgos.
- Orden de desarrollo.
- Criterios de prueba y aceptación.

---

# 5. Criterios de calidad documental

Cada documento deberá ser:

- Claro.
- Versionable.
- Auditable.
- Entendible para negocio y tecnología.
- Libre de ambigüedades comerciales.
- Útil para implementación futura.

Además, toda afirmación deberá clasificarse de una de estas formas:

- **Definida por cliente.**
- **Inferencia técnica.**
- **Propuesta de arquitectura.**
- **Decisión pendiente.**

---

# 6. Principios rectores del futuro sistema

Aunque por ahora no se implementará nada, la documentación se construirá bajo estos principios:

1. El frontend no debe ser la autoridad del cálculo oficial.
2. El backend deberá consolidar validación, consistencia y cálculo definitivo.
3. Las cotizaciones deberán evitar estados parciales o incompletos.
4. Cada categoría necesitará reglas explicitadas y verificables.
5. Los cálculos deberán ser trazables y reproducibles.
6. Los precios y fórmulas deberán quedar gobernados por documentación formal y no por lógica dispersa.

---

# 7. Resultado esperado al final de esta etapa

Al finalizar la documentación de Cotizaciones, Innovar deberá contar con:

- Un repositorio ordenado.
- Una arquitectura documental madura.
- Una especificación completa por categoría.
- Una base sólida para diseñar el motor backend.
- Un punto de partida confiable para continuar con el resto del software.
