# Taxonomía de Categorías — Sistema de Cotizaciones

## 1. Objetivo

Este documento define la estructura de categorías comerciales que integran el módulo **Cotizaciones** de Innovar App.

Su propósito es evitar duplicidades, ordenar el vocabulario del proyecto y establecer una base consistente para la documentación funcional y técnica posterior.

---

# 2. Módulo principal

## Cotizaciones

El módulo Cotizaciones agrupa todas las líneas comerciales que pueden transformarse en una propuesta económica formal para un cliente.

Cada línea comercial tendrá documentación independiente, porque sus fórmulas, parámetros, validaciones y configuraciones son diferentes.

---

# 3. Categorías oficiales iniciales

## 3.1 Cocinas Integrales

Categoría prioritaria y primera en documentarse.

Incluye reglas sobre:

- Tipos de cocina.
- Metraje lineal.
- Muebles inferiores y superiores.
- Módulos especiales.
- Mesones asociados.
- Descuentos.
- Costos complementarios.
- Ejemplos de cálculo.

## 3.2 Acabados Especiales

Categoría enfocada en tratamientos, materiales y mejoras específicas aplicables a productos del portafolio.

Ejemplos preliminares identificados:

- Pintado de puertas.
- Puertas de vidrio ahumado con marco de aluminio.
- Iluminación LED.
- Acabados brillantes, mate u otros.

## 3.3 Centro de TV

Categoría correspondiente a mobiliario de sala o entretenimiento.

La documentación futura deberá definir:

- Unidades de medida.
- Componentes base.
- Tipos de diseño.
- Materiales.
- Adicionales.
- Reglas de cálculo.

## 3.4 Closets

Categoría asociada a sistemas de almacenamiento.

La documentación futura deberá formalizar:

- Tipologías de closet.
- Medidas requeridas.
- Distribución interna.
- Puertas.
- Accesorios.
- Fórmulas de precio.

## 3.5 Puertas

Categoría de fabricación o reemplazo de frentes, puertas y tapas.

La documentación inicial del cliente ya menciona algunos valores de puertas y tapas para cocinas, pero aquí se tratará la categoría de manera autónoma cuando corresponda.

## 3.6 Mesones con Granito

Categoría independiente para mesones elaborados con granito y, si aplica, reglas comerciales que no dependan de una cocina integral completa.

Debe diferenciarse entre:

- Mesón incluido dentro de Cocina Integral.
- Mesón cotizado como categoría autónoma.

---

# 4. Regla de no duplicidad documental

Cuando un componente aparezca dentro de otra categoría, se documentará según su contexto.

Ejemplo:

- Un mesón dentro de Cocina Integral se documenta como parte del cálculo de esa cocina.
- Un mesón vendido de forma independiente se documenta en Mesones con Granito.

Esto evita mezclar reglas de contexto distinto.

---

# 5. Orden de prioridad documental

## Prioridad 1

- Cocinas Integrales.

## Prioridad 2

- Acabados Especiales.
- Mesones con Granito.

## Prioridad 3

- Closets.
- Puertas.
- Centro de TV.

El orden podrá ajustarse conforme se reciba documentación de negocio adicional.

---

# 6. Estructura documental esperada por categoría

Cada categoría deberá contar, al menos, con:

```text
README.md
00-fuente-de-verdad-normalizada.md
01-glosario.md
02-reglas-de-negocio.md
03-modelo-de-entradas.md
04-modelo-de-calculo.md
05-validaciones-y-excepciones.md
06-casos-de-prueba-funcionales.md
07-preguntas-abiertas.md
08-riesgos-y-decisiones.md
09-propuesta-de-contrato-futuro.md
```

---

# 7. Estado actual

| Categoría | Estado |
| --- | --- |
| Cocinas Integrales | En documentación activa |
| Acabados Especiales | Pendiente |
| Centro de TV | Pendiente |
| Closets | Pendiente |
| Puertas | Pendiente |
| Mesones con Granito | Pendiente |

---

# 8. Principio de crecimiento

La taxonomía podrá ampliarse en el futuro, pero cada nueva categoría deberá:

1. Justificar su independencia.
2. Tener reglas de negocio propias.
3. Evitar duplicidad innecesaria con categorías ya existentes.
4. Quedar documentada bajo la misma metodología estándar.
