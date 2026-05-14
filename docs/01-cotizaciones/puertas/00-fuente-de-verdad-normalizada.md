# Fuente de Verdad Normalizada — Puertas

## 1. Propósito del documento

Este documento transforma la información comercial original entregada por el cliente en una versión **ordenada, profesional y utilizable como base documental del sistema** para la categoría **Puertas**.

No constituye todavía una especificación técnica definitiva ni una implementación. Su función es:

- Conservar la intención original del cliente.
- Reorganizar la información por conceptos.
- Separar reglas, ejemplos y dudas.
- Preparar el trabajo posterior de reglas de negocio, modelos de cálculo y contratos de software.

---

# 2. Definición funcional de la categoría

Las **Puertas** son elementos individuales que se cotizan por unidad según:

1. Tipo de puerta.
2. Rango de ancho.
3. Cantidad.
4. Características descriptivas.
5. Inclusión opcional de transporte.

## 2.1 Forma general de cálculo

- Unidad principal: **unidad**.
- Fórmula general:

```text
Total Puertas = Cantidad × Precio por Unidad según tipo y rango de ancho
```

## 2.2 Tipos disponibles

- Puerta batiente.
- Puerta corrediza.

## 2.3 Variables complementarias

- Color de herrajes.
- Dintel.
- Altura.
- Ubicación.
- Notas personalizadas.

---

# 3. Tipos de puerta

## 3.1 Puerta batiente

### Precios

| Rango de ancho | Precio por unidad |
| --- | ---: |
| 50 a 85 cm | $890.000 COP |
| 85 a 110 cm | $950.000 COP |

### Características

- Se abre hacia afuera.
- Requiere espacio de apertura.
- Ideal para espacios amplios.
- Usa herrajes tipo bisagras.

### Fórmula

```text
Precio = Cantidad × Precio por Unidad
```

### Ejemplo

```text
2 puertas batientes de 80 cm
Precio = 2 × 890.000 = 1.780.000
```

---

## 3.2 Puerta corrediza

### Precios

| Rango de ancho | Precio por unidad |
| --- | ---: |
| 50 a 85 cm | $1.250.000 COP |
| 85 a 110 cm | $1.350.000 COP |

### Características

- Se desliza sobre rieles.
- Ocupa menos espacio.
- Ideal para espacios reducidos.
- Usa rieles y rodamientos.

### Fórmula

```text
Precio = Cantidad × Precio por Unidad
```

### Ejemplo

```text
1 puerta corrediza de 100 cm
Precio = 1 × 1.350.000 = 1.350.000
```

---

# 4. Tabla de precios por tipo y rango

| Tipo | Rango de ancho | Ancho típico | Precio / unidad |
| --- | --- | --- | ---: |
| Batiente | 50 a 85 cm | 60 a 80 cm | $890.000 COP |
| Batiente | 85 a 110 cm | 90 a 110 cm | $950.000 COP |
| Corrediza | 50 a 85 cm | 60 a 80 cm | $1.250.000 COP |
| Corrediza | 85 a 110 cm | 90 a 110 cm | $1.350.000 COP |

---

# 5. Accesorios y atributos descriptivos

## 5.1 Color de herrajes

### Opciones disponibles

- Aluminio.
- Negro.

### Regla de precio

El color de los herrajes **no genera recargo adicional**.

```text
Herrajes aluminio = mismo precio
Herrajes negros = mismo precio
```

---

## 5.2 Dintel

### Definición

Estructura superior que refuerza la puerta.

### Regla de precio

- Incluido en el precio de la puerta.
- Debe registrarse en la descripción o configuración si se incluye.

---

# 6. Determinación del rango de ancho

La fuente establece una regla condicional para determinar el rango de ancho:

```text
Si ancho <= 85 cm, entonces rango = 50-85
Si ancho > 85 cm, entonces rango = 85-110
```

## Observación documental crítica

La fuente define los rangos como:

- `50-85 cm`
- `85-110 cm`

Esto genera una ambigüedad en el valor exacto de **85 cm**, porque podría pertenecer a ambos rangos. Sin embargo, el pseudocódigo entregado asigna **85 cm al rango 50-85**.

Por ahora se normaliza así:

```text
50 cm <= ancho <= 85 cm  => rango 50-85
85 cm < ancho <= 110 cm  => rango 85-110
```

---

# 7. Fórmula general de cálculo

```text
Precio Puertas = Sumatoria de cada línea de puerta
```

Donde cada línea se calcula así:

```text
Línea = Cantidad × Precio Unitario según Tipo y Rango
```

## 7.1 Ejemplo 1

```text
3 puertas batientes de 75 cm
Rango = 50-85
Precio = 3 × 890.000 = 2.670.000
```

## 7.2 Ejemplo 2

```text
2 puertas corredizas de 95 cm
Rango = 85-110
Precio = 2 × 1.350.000 = 2.700.000
```

---

# 8. Tabla rápida de precios

## 8.1 Puertas batientes

| Cantidad | Rango 50-85 cm | Rango 85-110 cm |
| ---: | ---: | ---: |
| 1 | $890.000 | $950.000 |
| 2 | $1.780.000 | $1.900.000 |
| 3 | $2.670.000 | $2.850.000 |
| 4 | $3.560.000 | $3.800.000 |
| 5 | $4.450.000 | $4.750.000 |

## 8.2 Puertas corredizas

| Cantidad | Rango 50-85 cm | Rango 85-110 cm |
| ---: | ---: | ---: |
| 1 | $1.250.000 | $1.350.000 |
| 2 | $2.500.000 | $2.700.000 |
| 3 | $3.750.000 | $4.050.000 |
| 4 | $5.000.000 | $5.400.000 |
| 5 | $6.250.000 | $6.750.000 |

---

# 9. Transporte e imprevistos

## 9.1 Valor por defecto

- **$150.000 COP**.

## 9.2 Aplicación

- Opcional.
- Se suma al subtotal de puertas si se incluye.

## 9.3 Fórmula

```text
Total = Subtotal Puertas + Transporte
```

### Ejemplo

```text
2 puertas batientes de 80 cm
Puertas = 2 × 890.000 = 1.780.000
Transporte = 150.000
Total = 1.930.000
```

---

# 10. Casos de uso reales normalizados

## Caso 1 — Puertas batientes estándar

### Configuración

- Tipo: Batiente.
- Cantidad: 3.
- Ancho: 80 cm.
- Color herrajes: Aluminio.
- Dintel: Sí.
- Ubicaciones: Baño, Cocina, Recámara.
- Transporte: No.

### Cálculo

```text
3 × 890.000 = 2.670.000
Total = 2.670.000
```

---

## Caso 2 — Puertas corredizas grandes

### Configuración

- Tipo: Corrediza.
- Cantidad: 2.
- Ancho: 100 cm.
- Color herrajes: Negro.
- Dintel: No.
- Ubicaciones: Closet, Despensa.
- Transporte: Sí.

### Cálculo

```text
2 × 1.350.000 = 2.700.000
Transporte = 150.000
Total = 2.850.000
```

---

## Caso 3 — Mix de puertas

### Configuración

- 2 puertas batientes de 80 cm.
- 1 puerta corrediza de 90 cm.
- Herrajes: Aluminio.
- Transporte: Sí.

### Cálculo

```text
Batientes = 2 × 890.000 = 1.780.000
Corrediza = 1 × 1.350.000 = 1.350.000
Subtotal = 3.130.000
Transporte = 150.000
Total = 3.280.000
```

---

## Caso 4 — Puertas corredizas pequeñas

### Configuración

- Tipo: Corrediza.
- Cantidad: 4.
- Ancho: 70 cm.
- Color herrajes: Negro.
- Dintel: Sí.
- Ubicación: Armarios.
- Transporte: No.

### Cálculo

```text
4 × 1.250.000 = 5.000.000
Total = 5.000.000
```

---

# 11. Estructura documental del ítem de cotización

La fuente propone una estructura detallada para representar un ítem de puertas dentro de una cotización.

## 11.1 Campos generales del ítem

- Número de ítem.
- Tipo de ítem.
- Descripción.
- Cantidad.
- Precio unitario.
- Precio total.

## 11.2 Configuración específica

Cada puerta puede registrar:

- ID interno.
- Tipo.
- Rango de ancho.
- Ancho.
- Alto.
- Cantidad.
- Color de herrajes.
- Inclusión de dintel.
- Ubicación.
- Notas.
- Precio por unidad.
- Total de la línea.

La configuración general del grupo de puertas puede incluir:

- Subtotal.
- Transporte.
- Costo de transporte.
- Notas generales.

---

# 12. Validaciones principales

| Campo | Mínimo | Máximo |
| --- | ---: | ---: |
| Ancho | 50 cm | 110 cm |
| Alto | 1.80 m | 2.40 m |
| Cantidad | 1 | 20 por cotización |

---

# 13. Comparativa de tipos de puerta

| Aspecto | Batiente | Corrediza |
| --- | --- | --- |
| Precio 50-85 cm | $890.000 | $1.250.000 |
| Precio 85-110 cm | $950.000 | $1.350.000 |
| Tipo de apertura | Hacia afuera | Deslizante |
| Espacio requerido | Mayor | Menor |
| Uso típico | General | Espacios reducidos |
| Herrajes | Bisagras | Rieles |
| Perfil de precio | Económica | Premium |

---

# 14. Flujo de cotización con Puertas

1. Crear cotización.
2. Agregar ítem Puertas.
3. Agregar primera puerta.
4. Seleccionar tipo.
5. Ingresar ancho.
6. Ingresar alto.
7. Ingresar cantidad.
8. Seleccionar color de herrajes.
9. Indicar si incluye dintel.
10. Ingresar ubicación.
11. Calcular precio automático.
12. Agregar más puertas si aplica.
13. Incluir transporte si aplica.
14. Calcular subtotal.
15. Agregar otros ítems si aplica.
16. Calcular subtotal general.
17. Aplicar descuento si existe.
18. Generar total.
19. Enviar cotización.

---

# 15. Ejemplo completo de cotización normalizada

## Cliente

- Carlos Mendoza.
- Proyecto: Renovación de Puertas.

## Ítem 1 — Puertas batientes

```text
Cantidad: 3
Ancho: 80 cm
Rango: 50-85
Precio/unidad: 890.000
Ubicaciones: Baño, Cocina, Recámara
Herrajes: Aluminio
Dintel: Sí
Total ítem: 2.670.000
```

## Ítem 2 — Puertas corredizas

```text
Cantidad: 2
Ancho: 100 cm
Rango: 85-110
Precio/unidad: 1.350.000
Ubicaciones: Closet, Despensa
Herrajes: Negro
Dintel: No
Total ítem: 2.700.000
```

## Ítem 3 — Herrajes adicionales

```text
Descripción: Bisagras Premium + Rieles
Precio: 450.000
```

## Total cotización

```text
Subtotal general: 5.820.000
Transporte: 150.000
Descuento 5%: -299.500
Total final: 5.670.500
```

---

# 16. Puntos pendientes de resolución

1. Confirmar si el rango de ancho de 85 cm pertenece al primer rango, como sugiere el pseudocódigo, o si debe definirse de otra manera.
2. Confirmar si la altura de la puerta afecta el precio o si solo es un dato descriptivo dentro del rango permitido.
3. Determinar si dintel seguirá sin costo adicional en todos los casos.
4. Confirmar si el color de herrajes siempre será informativo y sin impacto de precio.
5. Definir si el límite de 20 puertas es regla comercial fija o límite operativo inicial.
6. Aclarar si herrajes adicionales deben formar una categoría o subítem independiente dentro de Puertas.

---

# 17. Cierre documental

Este documento consolida la primera versión profesional de la fuente de verdad funcional para **Puertas**.

Será la base para construir los siguientes documentos de la carpeta:

- Glosario.
- Reglas de negocio.
- Modelo de entradas.
- Modelo de cálculo.
- Validaciones.
- Casos de prueba.
- Riesgos y decisiones.
- Propuesta de contrato futuro.
