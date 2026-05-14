# Fuente de Verdad Normalizada — Closets

## 1. Propósito del documento

Este documento transforma la información comercial original entregada por el cliente en una versión **ordenada, profesional y utilizable como base documental del sistema** para la categoría **Closets**.

No constituye todavía una especificación técnica definitiva ni una implementación. Su función es:

- Conservar la intención original del cliente.
- Reorganizar la información por conceptos.
- Separar reglas, ejemplos y dudas.
- Preparar el trabajo posterior de reglas de negocio, modelos de cálculo y contratos de software.

---

# 2. Definición funcional de la categoría

El **Closet** es un mueble empotrado o modular cuya cotización se construye principalmente a partir de:

1. Tipo de closet.
2. Ancho y alto.
3. Área total en metros cuadrados.
4. Tipo de puertas.
5. Inclusión opcional de transporte.

## 2.1 Forma general de cálculo

- Unidad principal: **metro cuadrado (m²)**.
- Fórmula general:

```text
Área = Ancho × Alto
Precio Base = Área × Precio por m² según tipo de closet
Total = Precio Base + Transporte si aplica
```

## 2.2 Componentes incluidos

La fuente de verdad indica que todos los tipos de closet incluyen:

- Maletero.
- Divisor.
- Doble colgadero.
- Entrepaños.
- Doble cajonero.
- Zapatero.
- Puertas corredizas o batientes.

---

# 3. Tipos de closet

## 3.1 Closet Estándar

| Campo | Valor |
| --- | --- |
| Precio | $750.000 COP/m² |
| Profundidad | 0.60 cm según fuente original |
| Nivel | Básico |
| Descripción | Profundidad estándar |

### Fórmula

```text
Precio = Ancho × Alto × 750.000
```

### Ejemplo

```text
Ancho: 2.5 m
Alto: 2.4 m
Área: 2.5 × 2.4 = 6.0 m²
Precio: 6.0 × 750.000 = 4.500.000
```

---

## 3.2 Closet Especial

| Campo | Valor |
| --- | --- |
| Precio | $650.000 COP/m² |
| Profundidad | Hasta 0.45 cm según fuente original |
| Nivel | Económico |
| Descripción | Profundidad reducida |

### Fórmula

```text
Precio = Ancho × Alto × 650.000
```

### Ejemplo

```text
Ancho: 2.0 m
Alto: 2.4 m
Área: 2.0 × 2.4 = 4.8 m²
Precio: 4.8 × 650.000 = 3.120.000
```

---

## 3.3 Closet Empotrado

| Campo | Valor |
| --- | --- |
| Precio | $900.000 COP/m² |
| Profundidad | 0.60 cm según fuente original |
| Nivel | Premium |
| Descripción | Gama alta con espaldar y laterales completos |

### Componentes adicionales incluidos

Además de los componentes base, el closet empotrado incluye:

- Espaldar completo.
- Laterales completos.

### Fórmula

```text
Precio = Ancho × Alto × 900.000
```

### Ejemplo

```text
Ancho: 3.0 m
Alto: 2.4 m
Área: 3.0 × 2.4 = 7.2 m²
Precio: 7.2 × 900.000 = 6.480.000
```

---

# 4. Tabla de precios por m²

| Tipo | Precio/m² | Profundidad según fuente | Nivel |
| --- | ---: | --- | --- |
| Estándar | $750.000 | 0.60 cm | Básico |
| Especial | $650.000 | 0.45 cm | Económico |
| Empotrado | $900.000 | 0.60 cm | Premium |

## Observación documental crítica

La fuente usa la unidad **cm** al indicar profundidades de `0.60 cm` y `0.45 cm`, pero por contexto técnico y comercial parece referirse a **0.60 m** y **0.45 m**.

Este punto se registra como **pendiente de confirmación formal** antes de convertirlo en especificación técnica definitiva.

---

# 5. Tipos de puertas

## 5.1 Puertas corredizas

- Deslizan sobre rieles.
- Ocupan menos espacio.
- Son ideales para espacios reducidos.
- Están incluidas en el precio del closet.

## 5.2 Puertas batientes

- Se abren hacia afuera.
- Requieren más espacio libre.
- Ofrecen acceso más directo.
- Están incluidas en el precio del closet.

## 5.3 Regla comercial principal

El tipo de puerta **no genera recargo adicional**.

```text
Puertas corredizas = mismo precio
Puertas batientes = mismo precio
```

---

# 6. Cálculo de área

## 6.1 Fórmula

```text
Área (m²) = Ancho (m) × Alto (m)
```

## 6.2 Ejemplo base

```text
Ancho: 2.5 m
Alto: 2.4 m
Área: 2.5 × 2.4 = 6.0 m²
```

## 6.3 Áreas comunes de referencia

| Ancho | Alto | Área |
| --- | --- | ---: |
| 1.5 m | 2.4 m | 3.6 m² |
| 2.0 m | 2.4 m | 4.8 m² |
| 2.5 m | 2.4 m | 6.0 m² |
| 3.0 m | 2.4 m | 7.2 m² |
| 3.5 m | 2.4 m | 8.4 m² |
| 4.0 m | 2.4 m | 9.6 m² |

---

# 7. Tablas rápidas de precio

## 7.1 Closet Estándar — $750.000 COP/m²

| Ancho | Alto | Área | Precio |
| --- | --- | ---: | ---: |
| 1.5 m | 2.4 m | 3.6 m² | $2.700.000 |
| 2.0 m | 2.4 m | 4.8 m² | $3.600.000 |
| 2.5 m | 2.4 m | 6.0 m² | $4.500.000 |
| 3.0 m | 2.4 m | 7.2 m² | $5.400.000 |
| 3.5 m | 2.4 m | 8.4 m² | $6.300.000 |
| 4.0 m | 2.4 m | 9.6 m² | $7.200.000 |

---

## 7.2 Closet Especial — $650.000 COP/m²

| Ancho | Alto | Área | Precio |
| --- | --- | ---: | ---: |
| 1.5 m | 2.4 m | 3.6 m² | $2.340.000 |
| 2.0 m | 2.4 m | 4.8 m² | $3.120.000 |
| 2.5 m | 2.4 m | 6.0 m² | $3.900.000 |
| 3.0 m | 2.4 m | 7.2 m² | $4.680.000 |
| 3.5 m | 2.4 m | 8.4 m² | $5.460.000 |
| 4.0 m | 2.4 m | 9.6 m² | $6.240.000 |

---

## 7.3 Closet Empotrado — $900.000 COP/m²

| Ancho | Alto | Área | Precio |
| --- | --- | ---: | ---: |
| 1.5 m | 2.4 m | 3.6 m² | $3.240.000 |
| 2.0 m | 2.4 m | 4.8 m² | $4.320.000 |
| 2.5 m | 2.4 m | 6.0 m² | $5.400.000 |
| 3.0 m | 2.4 m | 7.2 m² | $6.480.000 |
| 3.5 m | 2.4 m | 8.4 m² | $7.560.000 |
| 4.0 m | 2.4 m | 9.6 m² | $8.640.000 |

---

# 8. Transporte e imprevistos

## 8.1 Valor por defecto

- **$150.000 COP**.

## 8.2 Aplicación

- Opcional.
- Se suma al subtotal del closet si se incluye.

## 8.3 Fórmula con transporte

```text
Total = (Área × Precio por m²) + Transporte
```

### Ejemplo

```text
Closet Estándar 2.5 m × 2.4 m
Área: 6.0 m²
Precio closet: 6.0 × 750.000 = 4.500.000
Transporte: 150.000
Total: 4.650.000
```

---

# 9. Casos de uso reales normalizados

## Caso 1 — Closet Estándar Pequeño

### Configuración

- Tipo: Estándar.
- Ancho: 1.5 m.
- Alto: 2.4 m.
- Puertas: Corredizas.
- Transporte: No.

### Cálculo

```text
Área = 1.5 × 2.4 = 3.6 m²
Precio = 3.6 × 750.000 = 2.700.000
Total = 2.700.000
```

---

## Caso 2 — Closet Empotrado Grande

### Configuración

- Tipo: Empotrado.
- Ancho: 3.5 m.
- Alto: 2.4 m.
- Puertas: Batientes.
- Transporte: Sí.

### Cálculo

```text
Área = 3.5 × 2.4 = 8.4 m²
Precio = 8.4 × 900.000 = 7.560.000
Transporte = 150.000
Total = 7.710.000
```

---

## Caso 3 — Closet Especial Mediano

### Configuración

- Tipo: Especial.
- Ancho: 2.5 m.
- Alto: 2.4 m.
- Puertas: Corredizas.
- Transporte: Sí.

### Cálculo

```text
Área = 2.5 × 2.4 = 6.0 m²
Precio = 6.0 × 650.000 = 3.900.000
Transporte = 150.000
Total = 4.050.000
```

---

## Caso 4 — Closet Estándar Grande

### Configuración

- Tipo: Estándar.
- Ancho: 4.0 m.
- Alto: 2.4 m.
- Puertas: Batientes.
- Transporte: No.

### Cálculo

```text
Área = 4.0 × 2.4 = 9.6 m²
Precio = 9.6 × 750.000 = 7.200.000
Total = 7.200.000
```

---

# 10. Estructura documental del ítem de cotización

La fuente propone una estructura detallada para representar un ítem de closet dentro de una cotización.

## 10.1 Campos generales del ítem

- Número de ítem.
- Tipo de ítem.
- Descripción.
- Cantidad.
- Precio unitario.
- Precio total.

## 10.2 Configuración específica

La configuración especializada contempla:

- Tipo de closet.
- Ancho.
- Alto.
- Tipo de puerta.
- Área calculada.
- Precio por m².
- Subtotal.
- Transporte.
- Costo de transporte.
- Notas personalizadas.

---

# 11. Validaciones principales

| Campo | Mínimo | Máximo |
| --- | ---: | ---: |
| Ancho | 0.5 m | 5.0 m |
| Alto | 1.5 m | 3.0 m |
| Área | 0.75 m² | 15.0 m² |

---

# 12. Comparativa de tipos de closet

| Aspecto | Estándar | Especial | Empotrado |
| --- | --- | --- | --- |
| Precio/m² | $750.000 | $650.000 | $900.000 |
| Profundidad según fuente | 0.60 cm | 0.45 cm | 0.60 cm |
| Espaldar/Laterales | No | No | Sí, completos |
| Accesorios | Básicos | Básicos | Premium |
| Nivel | Básico | Económico | Premium |
| Uso típico | General | Espacios reducidos | Lujo |

---

# 13. Notas personalizadas

La fuente indica que el ítem puede incluir notas como:

- Sin zapatero.
- Con espejo en puertas.
- Acabado especial.
- Con luz LED.

## Observación documental

Estas notas aparecen como texto descriptivo, pero no se establece si modifican o no el precio. Por ahora se consideran **notas informativas sin impacto automático**, salvo definición posterior.

---

# 14. Flujo de cotización con Closet

1. Crear cotización.
2. Agregar ítem Closet.
3. Seleccionar tipo.
4. Ingresar ancho.
5. Ingresar alto.
6. Calcular área automáticamente.
7. Seleccionar tipo de puertas.
8. Incluir transporte si aplica.
9. Calcular precio automático.
10. Agregar otros ítems si aplica.
11. Calcular subtotal general.
12. Aplicar descuento si existe.
13. Generar total.
14. Enviar cotización.

---

# 15. Ejemplo completo de cotización normalizada

## Cliente

- Juan Pérez.
- Proyecto: Closet Principal.

## Ítem 1 — Closet Empotrado

```text
Tipo: Empotrado
Ancho: 3.0 m
Alto: 2.4 m
Área: 7.2 m²
Precio/m²: 900.000
Subtotal: 6.480.000
Puertas: Batientes
Transporte: 150.000
Total ítem: 6.630.000
```

## Ítem 2 — Closet Estándar Secundario

```text
Tipo: Estándar
Ancho: 2.0 m
Alto: 2.4 m
Área: 4.8 m²
Precio/m²: 750.000
Subtotal: 3.600.000
Puertas: Corredizas
Transporte: 0
Total ítem: 3.600.000
```

## Total cotización

```text
Subtotal general: 10.230.000
Descuento 5%: -511.500
Total final: 9.718.500
```

---

# 16. Puntos pendientes de resolución

1. Confirmar la unidad correcta de profundidad: `0.60 cm` / `0.45 cm` o `0.60 m` / `0.45 m`.
2. Definir si los accesorios incluidos pueden variar sin afectar precio o si algunos cambios generan recargo o descuento.
3. Determinar si notas como “sin zapatero” o “con luz LED” deben pasar a ser configuraciones estructuradas con impacto en precio.
4. Confirmar si los tipos de puertas corredizas y batientes se mantienen siempre sin recargo.
5. Definir si transporte será siempre cargo fijo de $150.000 COP o si dependerá de ubicación, volumen u otra variable.
6. Confirmar si las áreas mínima y máxima serán reglas comerciales estrictas o límites operativos iniciales del sistema.

---

# 17. Cierre documental

Este documento consolida la primera versión profesional de la fuente de verdad funcional para **Closets**.

Será la base para construir los siguientes documentos de la carpeta:

- Glosario.
- Reglas de negocio.
- Modelo de entradas.
- Modelo de cálculo.
- Validaciones.
- Casos de prueba.
- Riesgos y decisiones.
- Propuesta de contrato futuro.
