# Fuente de Verdad Normalizada — Acabados Especiales

## 1. Propósito del documento

Este documento transforma la información comercial original entregada por el cliente en una versión **ordenada, profesional y utilizable como base documental del sistema** para la categoría **Acabados Especiales**.

No constituye todavía una especificación técnica definitiva ni una implementación. Su función es:

- Conservar la intención original del cliente.
- Reorganizar la información por conceptos.
- Separar reglas, ejemplos y dudas.
- Preparar el trabajo posterior de reglas de negocio, modelos de cálculo y contratos de software.

---

# 2. Definición funcional de la categoría

Los **Acabados Especiales** son complementos premium que se agregan principalmente a cocinas integrales para mejorar su funcionalidad y estética.

## 2.1 Componentes principales

La fuente de verdad define inicialmente dos componentes:

1. Puertas de aluminio + vidrio.
2. Iluminación LED.

## 2.2 Forma general de cálculo

- Puertas de aluminio + vidrio: cálculo por **metro cuadrado (m²)**.
- Iluminación LED: cálculo por **metro lineal (ml)**.

## 2.3 Aplicación comercial

- Son opcionales.
- Se agregan al precio base de la cocina o como ítem adicional dentro de la cotización.
- Sus precios dependen del componente y la configuración seleccionada.

---

# 3. Puertas de aluminio + vidrio

## 3.1 Descripción funcional

Puertas con marco de aluminio y vidrio templado para:

- Alacenas.
- Muebles especiales.
- Frentes premium dentro de una cocina integral.

## 3.2 Unidad de cálculo

- Metro cuadrado (**m²**).

## 3.3 Precio base

- **$1.200.000 COP por m².**

## 3.4 Bisagras adicionales

- Precio: **$15.000 COP por par**.

## 3.5 Fórmula documental de precio por puerta

```text
Precio Puerta = (Altura × Ancho × 1.200.000) + Precio Bisagras
```

Donde:

- Altura se expresa en metros.
- Ancho se expresa en metros.
- Precio Bisagras depende de la altura de la puerta.

---

# 4. Determinación de bisagras por altura

| Altura de puerta | Cantidad de pares de bisagras | Precio |
| --- | ---: | ---: |
| Hasta 0.80 m | 1 par | $15.000 COP |
| 0.81 m a 1.40 m | 2 pares | $30.000 COP |
| Mayor a 1.40 m | 3 pares | $45.000 COP |

## 4.1 Regla funcional

El número de pares de bisagras se determina automáticamente según la altura de la puerta.

---

# 5. Ejemplos de puertas de aluminio + vidrio

## 5.1 Puerta pequeña

### Configuración

- Altura: 0.60 m.
- Ancho: 0.50 m.

### Cálculo

```text
Área = 0.60 × 0.50 = 0.30 m²
Precio base = 0.30 × 1.200.000 = 360.000
Bisagras = 1 par = 15.000
Total = 375.000
```

---

## 5.2 Puerta mediana

### Configuración

- Altura: 1.00 m.
- Ancho: 0.60 m.

### Cálculo

```text
Área = 1.00 × 0.60 = 0.60 m²
Precio base = 0.60 × 1.200.000 = 720.000
Bisagras = 2 pares = 30.000
Total = 750.000
```

---

## 5.3 Puerta grande

### Configuración

- Altura: 1.50 m.
- Ancho: 0.80 m.

### Cálculo

```text
Área = 1.50 × 0.80 = 1.20 m²
Precio base = 1.20 × 1.200.000 = 1.440.000
Bisagras = 3 pares = 45.000
Total = 1.485.000
```

---

# 6. Tabla rápida de precios de puertas

| Dimensiones | Área | Precio base puerta | Bisagras | Total |
| --- | ---: | ---: | ---: | ---: |
| 0.60 m × 0.50 m | 0.30 m² | $360.000 | $15.000 | $375.000 |
| 0.80 m × 0.60 m | 0.48 m² | $576.000 | $15.000 | $591.000 |
| 1.00 m × 0.60 m | 0.60 m² | $720.000 | $30.000 | $750.000 |
| 1.20 m × 0.80 m | 0.96 m² | $1.152.000 | $30.000 | $1.182.000 |
| 1.50 m × 0.80 m | 1.20 m² | $1.440.000 | $45.000 | $1.485.000 |
| 1.80 m × 1.00 m | 1.80 m² | $2.160.000 | $45.000 | $2.205.000 |
| 2.00 m × 1.00 m | 2.00 m² | $2.400.000 | $45.000 | $2.445.000 |

---

# 7. Iluminación LED

## 7.1 Descripción funcional

Iluminación LED integrada en:

- Alacenas.
- Muebles especiales.
- Componentes premium de cocina.

## 7.2 Unidad de cálculo

- Metro lineal (**ml**).

## 7.3 Precio base

- **$150.000 COP por ml.**

## 7.4 Regla de aplicación

La fuente especifica que la iluminación LED se instala sobre el lado largo del mueble.

## 7.5 Fórmula documental

```text
Precio LED = Metros Lineales × 150.000
```

---

# 8. Ejemplos de iluminación LED

## 8.1 Ejemplo base

```text
2.5 ml × 150.000 = 375.000
```

## 8.2 Tabla de referencia

| Metraje LED | Precio | Uso típico |
| --- | ---: | --- |
| 1.0 ml | $150.000 | Alacena pequeña |
| 1.5 ml | $225.000 | Alacena mediana |
| 2.0 ml | $300.000 | Alacena grande |
| 2.5 ml | $375.000 | Mueble completo |
| 3.0 ml | $450.000 | Mueble doble |

## 8.3 Tabla ampliada de precios rápidos

| Metraje LED | Precio |
| --- | ---: |
| 0.5 ml | $75.000 |
| 1.0 ml | $150.000 |
| 1.5 ml | $225.000 |
| 2.0 ml | $300.000 |
| 2.5 ml | $375.000 |
| 3.0 ml | $450.000 |
| 3.5 ml | $525.000 |
| 4.0 ml | $600.000 |

---

# 9. Fórmula general de Acabados Especiales

La categoría puede expresarse así:

```text
Total Acabados Especiales = Total Puertas Aluminio + Vidrio + Total LED
```

Donde:

```text
Total Puertas = Sumatoria de cada puerta calculada individualmente
Total LED = Metros LED × 150.000
```

---

# 10. Casos de uso reales normalizados

## Caso 1 — Acabado Especial Simple

### Configuración

- 1 puerta de aluminio + vidrio de 0.80 m × 0.60 m.
- Sin LED.

### Cálculo

```text
Área puerta = 0.80 × 0.60 = 0.48 m²
Precio base = 0.48 × 1.200.000 = 576.000
Bisagras = 1 par = 15.000
Total acabados = 591.000
```

---

## Caso 2 — Acabado Especial Completo

### Configuración

- Puerta 1: 1.00 m × 0.60 m.
- Puerta 2: 1.20 m × 0.80 m.
- LED: 2.5 ml.

### Cálculo

```text
Puerta 1 = 750.000
Puerta 2 = 1.182.000
LED = 375.000
Total acabados = 2.307.000
```

---

## Caso 3 — Acabado Especial Premium

### Configuración

- Puerta 1: 0.80 m × 0.60 m.
- Puerta 2: 1.00 m × 0.80 m.
- Puerta 3: 1.50 m × 1.00 m.
- LED: 3.5 ml.

### Cálculo

```text
Puerta 1 = 591.000
Puerta 2 = 990.000
Puerta 3 = 1.845.000
LED = 525.000
Total acabados = 3.951.000
```

---

## Caso 4 — Mix de Acabados en Cocina Integral

### Cocina base

- Tipo: Cocina completa.
- Metraje: 3.5 ml.
- Precio base informado: $4.200.000 COP.

### Acabados especiales

- Puerta 1: 1.20 m × 0.80 m = $1.182.000 COP.
- Puerta 2: 1.00 m × 0.60 m = $750.000 COP.
- LED: 2.5 ml = $375.000 COP.

### Total

```text
Total acabados especiales = 2.307.000
Precio final cocina + acabados = 6.507.000
```

---

# 11. Estructura documental del ítem de cotización

La fuente propone una representación estructurada para el ítem **Acabados Especiales**.

## 11.1 Campos generales del ítem

- Número de ítem.
- Tipo de ítem.
- Descripción.
- Cantidad.
- Precio unitario.
- Precio total.

## 11.2 Configuración específica

La configuración especializada contempla:

- Estado habilitado del módulo.
- Lista de puertas de aluminio + vidrio.
- Dimensiones de cada puerta.
- Área calculada de cada puerta.
- Número de bisagras por puerta.
- Configuración de LED.
- Metraje de LED.

---

# 12. Validaciones principales

| Campo | Mínimo | Máximo |
| --- | ---: | ---: |
| Altura puerta | 0.50 m | 2.00 m |
| Ancho puerta | 0.30 m | 1.50 m |
| Metraje LED | 0.1 ml | 10 ml |
| Cantidad de puertas | 0 | 10 |

---

# 13. Flujo de cotización con Acabados Especiales

1. Crear cotización.
2. Agregar ítem Cocina Integral.
3. Agregar ítem Acabados Especiales si aplica.
4. Habilitar puertas de aluminio + vidrio.
5. Ingresar dimensiones de cada puerta.
6. Calcular bisagras automáticamente.
7. Calcular precio de cada puerta.
8. Habilitar LED si aplica.
9. Ingresar metraje LED.
10. Calcular total de acabados.
11. Sumar al subtotal general.
12. Aplicar descuento si existe.
13. Generar total final.
14. Enviar cotización.

---

# 14. Ejemplo completo de cotización normalizada

## Cliente

- Patricia González.
- Proyecto: Cocina Integral Premium con Acabados Especiales.

## Ítem 1 — Cocina Integral

```text
Tipo: Completa
Metraje: 3.5 ml
Precio: 4.200.000
```

## Ítem 2 — Acabados Especiales

```text
Puerta 1: 1.00 × 0.60 = 750.000
Puerta 2: 1.20 × 0.80 = 1.182.000
LED: 2.5 ml = 375.000
Total acabados = 2.307.000
```

## Total cotización

```text
Subtotal general = 6.507.000
Descuento 10% = -650.700
Total final = 5.856.300
```

---

# 15. Comparativa de componentes

| Componente | Precio | Aplicación | Beneficio |
| --- | ---: | --- | --- |
| Puertas Aluminio + Vidrio | $1.200.000 COP/m² | Alacenas | Estética moderna y durabilidad |
| Bisagras | $15.000 COP/par | Puertas | Funcionalidad y calidad |
| Iluminación LED | $150.000 COP/ml | Alacenas | Iluminación ambiental y funcional |

---

# 16. Puntos pendientes de resolución

1. Confirmar si esta categoría se mantiene estrictamente como complemento de cocinas o si podrá cotizarse también de forma autónoma.
2. Confirmar si la regla de bisagras representa pares totales requeridos o pares adicionales sobre una base estándar.
3. Definir si el sistema debe permitir puertas con alturas o anchos fuera de los rangos propuestos bajo autorización especial.
4. Determinar si el precio por puerta debe redondearse a enteros al final de cada puerta o solo al total del ítem.
5. Confirmar si la cantidad máxima de 10 puertas es regla comercial fija o límite operativo del primer modelo.

---

# 17. Cierre documental

Este documento consolida la primera versión profesional de la fuente de verdad funcional para **Acabados Especiales**.

Será la base para construir los siguientes documentos de la carpeta:

- Glosario.
- Reglas de negocio.
- Modelo de entradas.
- Modelo de cálculo.
- Validaciones.
- Casos de prueba.
- Riesgos y decisiones.
- Propuesta de contrato futuro.
