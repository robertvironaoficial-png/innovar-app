# Fuente de Verdad Normalizada — Centro de TV

## 1. Propósito del documento

Este documento transforma la información comercial original entregada por el cliente en una versión **ordenada, profesional y utilizable como base documental del sistema** para la categoría **Centro de TV**.

No constituye todavía una especificación técnica definitiva ni una implementación. Su función es:

- Conservar la intención original del cliente.
- Reorganizar la información por conceptos.
- Separar reglas, ejemplos y dudas.
- Preparar el trabajo posterior de reglas de negocio, modelos de cálculo y contratos de software.

---

# 2. Definición funcional de la categoría

El **Centro de TV** es un mueble flotante especializado para salas de estar. Su cotización se compone de:

1. Precio base según ancho.
2. Componentes incluidos de manera estándar.
3. Opcionales y recargos.
4. Transporte e imprevistos, si se seleccionan.

## 2.1 Componentes generales del producto

El producto se compone de:

- Mueble flotante.
- Panel para TV.
- Repisas flotantes.

## 2.2 Parámetros principales

- Ancho variable entre **1.20 m** y **2.40 m**.
- Acabado Alto Brillo opcional.
- Iluminación LED opcional.
- Cantidad variable de repisas.
- Cantidad variable de espacios para equipos.
- Transporte opcional.

---

# 3. Precio base por ancho

## 3.1 Medida estándar

- **Ancho estándar:** 1.60 m.
- **Precio base estándar:** $2.800.000 COP.

## 3.2 Regla de variación por ancho

La fuente establece un ajuste de:

- **$500.000 COP por cada 20 cm** de diferencia frente al ancho estándar de 1.60 m.

## 3.3 Tabla normalizada de precios por ancho

| Ancho | Variación frente a 1.60 m | Precio |
| --- | ---: | ---: |
| 1.20 m | -40 cm | $1.800.000 COP |
| 1.40 m | -20 cm | $2.300.000 COP |
| 1.60 m | Estándar | $2.800.000 COP |
| 1.80 m | +20 cm | $3.300.000 COP |
| 2.00 m | +40 cm | $3.800.000 COP |
| 2.20 m | +60 cm | $4.300.000 COP |
| 2.40 m | +80 cm | $4.800.000 COP |

## 3.4 Fórmula documental

```text
Precio Base = 2.800.000 + (Número de incrementos de 20 cm × 500.000)
```

Donde:

```text
Número de incrementos = (Ancho - 1.60) / 0.20
```

## 3.5 Ejemplo

Centro de TV de 2.00 m:

```text
Diferencia = 2.00 - 1.60 = 0.40 m
Incrementos = 0.40 / 0.20 = 2
Precio base = 2.800.000 + (2 × 500.000) = 3.800.000
```

---

# 4. Componentes incluidos en el precio base

## 4.1 Mueble flotante

Incluye:

- Estructura principal.
- Soporte de pared.
- Acabado estándar.

## 4.2 Panel para TV

Incluye:

- Panel trasero.
- Alistonado decorativo.
- Espacio para TV.

## 4.3 Repisas flotantes

Incluye de forma estándar:

- **2 repisas flotantes.**
- Capacidad de carga estándar.
- Acabado coordinado con el mueble.

---

# 5. Opcionales y recargos

## 5.1 Acabado Alto Brillo

### Regla principal informada

- Recargo base informado: **+$350.000 COP**.

### Nota complementaria del cliente

La fuente también menciona que el acabado alto brillo podría relacionarse con el precio de tapas de cocina pintadas al poliuretano y que podría requerir detallar cantidad de piezas, con un valor aproximado de **$90.000 COP por pieza**.

## Normalización documental

Por ahora se conserva como regla principal:

```text
Alto Brillo = +$350.000 COP
```

Y se marca como **pendiente de decisión** si en el futuro:

- Se mantiene el recargo fijo.
- Se calcula por cantidad de piezas pintadas.
- Se permite escoger entre ambas modalidades.

---

## 5.2 Iluminación LED

### Regla informada en la descripción

- Precio: **+$220.000 COP por metro lineal**.

### Regla usada en las tablas y fórmulas de ejemplo

- Precio fijo: **+$250.000 COP**.

## Observación documental crítica

La fuente presenta una contradicción entre:

1. LED por metro lineal a $220.000 COP/ml.
2. LED fijo de $250.000 COP usado en fórmulas y ejemplos.

Por ahora se registra como **pendiente de validación comercial**. En la documentación de cálculo posterior se deberán presentar ambas posibilidades y solicitar cierre de regla.

---

## 5.3 Repisas flotantes

### Regla base

- El Centro de TV incluye **2 repisas** en el precio base.

### Precio por repisa adicional

- **+$100.000 COP** por repisa adicional por encima de las 2 incluidas.

### Regla de reducción por menos repisas

La fuente también indica:

| Cantidad de repisas | Ajuste |
| --- | ---: |
| 0 repisas | -$200.000 COP |
| 1 repisa | -$100.000 COP |
| 2 repisas | Incluidas |
| 3 repisas | +$100.000 COP |
| 4 repisas | +$200.000 COP |
| 5 repisas | +$300.000 COP |

## Fórmula documental completa

```text
Precio Repisas = (Cantidad de Repisas - 2) × 100.000
```

Esta fórmula produce:

- Valores negativos cuando se seleccionan menos de 2 repisas.
- Valor 0 con 2 repisas.
- Valores positivos con más de 2 repisas.

### Ejemplo

```text
Cantidad de repisas: 4
Repisas adicionales: 4 - 2 = 2
Precio repisas: 2 × 100.000 = 200.000
```

## Observación documental

En el pseudocódigo aportado por la fuente se usa `MAX(0, repisas - 2)`, lo cual **no aplica descuentos** cuando se seleccionan 0 o 1 repisa. Esto contradice la tabla comercial que sí contempla reducciones.

Este punto debe cerrarse antes de convertir la lógica a especificación de software.

---

## 5.4 Espacios para equipos

### Definición

Compartimentos especiales para:

- Consolas de videojuegos.
- Decodificadores.
- Receptores.
- Equipos de sonido.

### Rango permitido

- Mínimo: 0.
- Máximo: 4.

### Precio

- **+$150.000 COP por espacio.**

### Fórmula

```text
Precio Equipos = Cantidad de Espacios × 150.000
```

### Ejemplo

```text
2 espacios × 150.000 = 300.000
```

---

# 6. Transporte e imprevistos

## 6.1 Valor por defecto

- **$150.000 COP**.

## 6.2 Aplicación

- Opcional.
- Se suma al subtotal si se incluye.

## 6.3 Fórmula

```text
Total = Subtotal sin transporte + Transporte
```

### Ejemplo del cliente

Centro TV 1.60 m + Alto Brillo + LED + Transporte:

```text
Base: 2.800.000
Alto Brillo: 350.000
LED: 250.000
Transporte: 150.000
Total: 3.550.000
```

---

# 7. Fórmula general de la categoría

De forma documental, el total del ítem puede expresarse así:

```text
Total Centro TV = Precio Base por Ancho
                + Ajuste por Repisas
                + Alto Brillo
                + LED
                + Espacios para Equipos
                + Transporte si aplica
```

## 7.1 Subtotal de ítem

```text
Subtotal Item = Base + Repisas + Alto Brillo + LED + Equipos + Transporte
```

---

# 8. Casos de uso reales normalizados

## Caso 1 — Centro TV Estándar Básico

### Configuración

- Ancho: 1.60 m.
- Repisas: 2.
- Alto Brillo: No.
- LED: No.
- Espacios para equipos: 0.
- Transporte: No.

### Cálculo

```text
Precio base: 2.800.000
Total: 2.800.000
```

---

## Caso 2 — Centro TV Premium Completo

### Configuración

- Ancho: 2.00 m.
- Repisas: 4.
- Alto Brillo: Sí.
- LED: Sí.
- Espacios para equipos: 2.
- Transporte: Sí.

### Cálculo

```text
Precio base: 3.800.000
Repisas extra: 200.000
Alto Brillo: 350.000
LED: 250.000
Espacios equipos: 300.000
Transporte: 150.000
Total: 5.050.000
```

---

## Caso 3 — Centro TV Pequeño Económico

### Configuración

- Ancho: 1.20 m.
- Repisas: 2.
- Alto Brillo: No.
- LED: No.
- Espacios para equipos: 1.
- Transporte: No.

### Cálculo

```text
Precio base: 1.800.000
Espacios equipos: 150.000
Total: 1.950.000
```

---

## Caso 4 — Centro TV Grande con Iluminación

### Configuración

- Ancho: 2.40 m.
- Repisas: 3.
- Alto Brillo: Sí.
- LED: Sí.
- Espacios para equipos: 0.
- Transporte: Sí.

### Cálculo

```text
Precio base: 4.800.000
Repisa extra: 100.000
Alto Brillo: 350.000
LED: 250.000
Transporte: 150.000
Total: 5.650.000
```

---

## Caso 5 — Centro TV Mediano Completo

### Configuración

- Ancho: 1.80 m.
- Repisas: 5.
- Alto Brillo: Sí.
- LED: Sí.
- Espacios para equipos: 3.
- Transporte: Sí.

### Cálculo

```text
Precio base: 3.300.000
Repisas extra: 300.000
Alto Brillo: 350.000
LED: 250.000
Espacios equipos: 450.000
Transporte: 150.000
Total: 4.800.000
```

---

# 9. Estructura documental del ítem de cotización

La fuente propone una estructura detallada para representar un ítem de Centro de TV dentro de una cotización.

## 9.1 Campos generales del ítem

- Número de ítem.
- Tipo de ítem.
- Descripción.
- Cantidad.
- Precio unitario.
- Precio total.

## 9.2 Configuración específica

La configuración especializada contempla:

- Ancho.
- Precio base.
- Alto brillo.
- Precio de alto brillo.
- LED.
- Precio de LED.
- Cantidad de repisas.
- Precio por repisas adicionales.
- Cantidad de espacios para equipos.
- Precio de espacios para equipos.
- Inclusión de transporte.
- Costo de transporte.
- Notas personalizadas.
- Subtotal.

---

# 10. Validaciones principales

| Campo | Mínimo | Máximo |
| --- | ---: | ---: |
| Ancho | 1.20 m | 2.40 m |
| Repisas | 0 | 5 |
| Espacios para equipos | 0 | 4 |

## Observación documental adicional

La tabla de precios por ancho solo contempla incrementos de 20 cm. Por lo tanto, deberá definirse si el sistema:

- Solo acepta medidas discretas: 1.20, 1.40, 1.60, 1.80, 2.00, 2.20 y 2.40.
- O si acepta valores intermedios y los redondea.

La fuente usa pseudocódigo con redondeo de incrementos, pero comercialmente la tabla sugiere medidas discretas.

---

# 11. Flujo de cotización

1. Crear cotización.
2. Agregar ítem Centro de TV.
3. Seleccionar ancho.
4. Seleccionar cantidad de repisas.
5. Elegir Alto Brillo.
6. Elegir LED.
7. Seleccionar espacios para equipos.
8. Elegir transporte.
9. Calcular precio automático.
10. Agregar otros ítems si aplica.
11. Calcular subtotal general.
12. Aplicar descuento si existe.
13. Generar total.
14. Enviar cotización.

---

# 12. Ejemplo de cotización completa normalizada

## Cliente

- Roberto Silva.
- Proyecto: Sala de Estar Moderna.

## Ítem 1 — Centro de TV

```text
Ancho: 2.00 m
Precio base: 3.800.000
Repisas: 4
Precio repisas: 200.000
Alto Brillo: 350.000
LED: 250.000
Espacios equipos: 300.000
Transporte: 150.000
Total ítem: 5.050.000
```

## Ítem 2 — Herrajes Especiales

```text
Descripción: Soportes de acero inoxidable
Precio: 200.000
```

## Total cotización

```text
Subtotal general: 5.250.000
Descuento 10%: -525.000
Total final: 4.725.000
```

---

# 13. Comparativa de opcionales

| Opcional | Precio informado | Beneficio |
| --- | ---: | --- |
| Alto Brillo | $350.000 COP | Acabado premium y durabilidad |
| LED | $250.000 COP en ejemplos / $220.000 COP/ml en descripción | Iluminación ambiental |
| Repisa Extra | $100.000 COP | Más espacio de almacenamiento |
| Espacio Equipo | $150.000 COP | Compartimento especializado |

---

# 14. Puntos pendientes de resolución

1. Confirmar si LED se cobra como valor fijo de $250.000 COP o como $220.000 COP por metro lineal.
2. Confirmar si Alto Brillo se mantiene como cargo fijo de $350.000 COP o si debe calcularse por piezas pintadas.
3. Definir si la reducción de precio por 0 o 1 repisa se aplica efectivamente.
4. Definir si el ancho debe limitarse a valores discretos de la tabla o permitir cualquier valor intermedio dentro del rango.
5. Aclarar la diferencia entre la regla de flujo que menciona variaciones de -$250.000 y la tabla principal que usa tramos de $500.000.
6. Establecer si transporte se maneja siempre como cargo fijo opcional de $150.000 COP.
7. Determinar si los herrajes especiales forman parte de esta categoría o se documentan como ítems externos combinables.

---

# 15. Cierre documental

Este documento consolida la primera versión profesional de la fuente de verdad funcional para **Centro de TV**.

Será la base para construir los siguientes documentos de la carpeta:

- Glosario.
- Reglas de negocio.
- Modelo de entradas.
- Modelo de cálculo.
- Validaciones.
- Casos de prueba.
- Riesgos y decisiones.
- Propuesta de contrato futuro.
