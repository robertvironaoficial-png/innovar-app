# Metodología de Documentación — Módulo Cotizaciones

## 1. Objetivo

Este documento define la metodología estándar para convertir información comercial y operativa del cliente en documentación profesional de producto y arquitectura futura.

La metodología se aplicará primero a **Cocinas Integrales** y luego al resto de categorías del módulo Cotizaciones.

---

# 2. Fuentes de información

Cada categoría se documentará a partir de una o más fuentes:

1. Documentación entregada por el cliente.
2. Aclaraciones posteriores del cliente.
3. Contexto de uso del producto.
4. Inferencias técnicas explícitamente marcadas como tales.
5. Decisiones de arquitectura propuestas para futura implementación.

---

# 3. Clasificación de cada afirmación

Para evitar ambigüedades, cada regla o definición deberá distinguir entre:

## 3.1 Definido por cliente

Información expresamente entregada como regla de negocio.

## 3.2 Interpretación funcional

Normalización del lenguaje comercial a términos entendibles para producto y tecnología.

## 3.3 Propuesta técnica

Sugerencia de diseño futura que aún no representa una decisión final de implementación.

## 3.4 Pendiente de validación

Punto ambiguo, incompleto o contradictorio que requiere confirmación.

---

# 4. Proceso documental por categoría

## Paso 1 — Recepción de la fuente de verdad

Se recibe la documentación del cliente sin modificar su intención.

## Paso 2 — Limpieza conceptual

Se ordenan:

- Términos.
- Flujos.
- Fórmulas.
- Unidades de medida.
- Tablas de precio.
- Casos especiales.

## Paso 3 — Identificación de contradicciones

Se detectan reglas que:

- Se pisan entre sí.
- Cambian según el ejemplo.
- No tienen unidad clara.
- No definen fórmula exacta.
- Mezclan conceptos de categorías distintas.

## Paso 4 — Normalización funcional

Se produce una versión estructurada y profesional de la fuente.

## Paso 5 — Traducción hacia arquitectura futura

Sin crear código todavía, se documenta:

- Entradas del sistema.
- Cálculos esperados.
- Salidas.
- Validaciones.
- Posibles responsabilidades futuras de backend.
- Posibles responsabilidades futuras de frontend.

## Paso 6 — Definición de preguntas abiertas

Toda ambigüedad se concentra en un documento específico para resolverla de forma ordenada.

## Paso 7 — Cierre de categoría

La categoría se considera lista cuando sus reglas pueden ser explicadas, probadas y transformadas en especificación de software sin improvisaciones.

---

# 5. Documentos estándar por categoría

## README.md

Explica el propósito de la categoría y su estado documental.

## 00-fuente-de-verdad-normalizada.md

Transforma la fuente original del cliente en una estructura funcional clara.

## 01-glosario.md

Define vocabulario y conceptos comerciales.

## 02-reglas-de-negocio.md

Expone reglas precisas y jerarquizadas.

## 03-modelo-de-entradas.md

Lista datos que el sistema necesitaría recibir.

## 04-modelo-de-calculo.md

Formaliza fórmulas, subtotales y totalizadores.

## 05-validaciones-y-excepciones.md

Define restricciones, errores y combinaciones inválidas.

## 06-casos-de-prueba-funcionales.md

Convierte los ejemplos de negocio en escenarios verificables.

## 07-preguntas-abiertas.md

Consolida dudas que deben resolverse antes de implementación.

## 08-riesgos-y-decisiones.md

Documenta impactos de decisiones incompletas o ambiguas.

## 09-propuesta-de-contrato-futuro.md

Resume cómo debería conversar la futura interfaz con el motor backend.

---

# 6. Estilo documental

La documentación debe:

- Usar lenguaje claro.
- Evitar tecnicismos innecesarios.
- Mantener tablas cuando ayuden a comparar.
- Separar reglas de ejemplos.
- Diferenciar regla general y excepción.
- Evitar mezclar categorías sin aviso explícito.
- Registrar dudas sin resolverlas de forma arbitraria.

---

# 7. Criterios de revisión

Antes de cerrar una categoría, revisar:

1. ¿La terminología es consistente?
2. ¿Las fórmulas pueden ejecutarse sin interpretación adicional?
3. ¿Los rangos y límites están claros?
4. ¿Los ejemplos coinciden con la regla general?
5. ¿Se identificaron contradicciones?
6. ¿Se separó lo definido por cliente de lo propuesto técnicamente?
7. ¿La documentación sirve a negocio, producto y desarrollo?

---

# 8. Resultado esperado

El resultado no será solo una colección de notas, sino una **base documental profesional** que permita diseñar el sistema con criterio, reducir errores futuros y construir un motor de cotización confiable.
