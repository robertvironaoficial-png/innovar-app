# Fuente de Verdad Normalizada — Mesones

## 1. Propósito del documento

Este documento organiza de forma profesional la información comercial entregada por el cliente para la categoría **Mesones** dentro del módulo **Cotizaciones**.

La fuente cubre tres líneas principales:

1. Mesón estándar.
2. Isla.
3. Barra.

También define materiales, profundidades, opcionales, fórmulas de cálculo, validaciones y casos reales.

---

# 2. Definición funcional de la categoría

Los **Mesones** son superficies de trabajo cotizadas principalmente por **metro lineal (ml)**, con variaciones según:

- Tipo de mesón.
- Material.
- Profundidad o fondo.
- Opcionales asociados.

## 2.1 Tipos de mesón

| Tipo | Uso principal |
| --- | --- |
| Mesón estándar | Cocina principal, normalmente pegado a pared |
| Isla | Centro de cocina, acceso por varios lados |
| Barra | Superficie auxiliar, normalmente pegada a pared |

## 2.2 Materiales disponibles

- Granito.
- Cuarzo.
- Sinterizado.

## 2.3 Variables de cálculo principales

- Metros lineales.
- Fondo en centímetros.
- Material.
- Tipo de mesón.
- Inclusión de laterales.
- Inclusión de regrueso.
- Salpicadero alto.
- Altura lateral de barra.
- Transporte.

---

# 3. Precios base por material

## 3.1 Precio estándar por metro lineal

| Material | Precio estándar / ml |
| --- | ---: |
| Granito | $700.000 COP |
| Cuarzo | $850.000 COP |
| Sinterizado | $1.200.000 COP |

## 3.2 Precio de barra angosta entre 35 y 45 cm

| Material | Precio barra angosta / ml |
| --- | ---: |
| Granito | $490.000 COP |
| Cuarzo | $600.000 COP |
| Sinterizado | $1.000.000 COP |

---

# 4. Multiplicadores por profundidad

La profundidad modifica el precio del mesón mediante multiplicadores.

| Fondo | Multiplicador | Interpretación |
| --- | ---: | --- |
| 55 a 65 cm | 1.0 | Estándar |
| 66 a 90 cm | 1.3 | Recargo del 30% |
| 91 a 120 cm | 2.0 | Precio doble |

## 4.1 Regla especial de barra angosta

La barra con fondo entre **35 y 45 cm** siempre usa:

```text
Multiplicador = 1.0
```

## 4.2 Fórmula general

```text
Precio Base Calculado = Precio por ml × Multiplicador × Metros Lineales
```

### Ejemplo

Mesón de granito de 2.5 ml con fondo de 80 cm:

```text
Precio = 2.5 × 700.000 × 1.3 = 2.275.000
```

---

# 5. Tipo 1 — Mesón estándar

## 5.1 Uso

Cocina principal, normalmente pegada a pared.

## 5.2 Componentes incluidos

- Mesón principal.
- Lavaplatos pegado.
- Salpicadero bajo de 10 cm.
- Regrueso en el visto.

## 5.3 Opcionales

- Salpicadero alto, que reemplaza el salpicadero bajo y duplica el metraje de cobro de esa superficie.

## 5.4 Profundidad válida

- 55 cm a 120 cm.

## 5.5 Fórmula base

```text
Total Mesón Estándar = Metros Lineales × Precio Base × Multiplicador + Lavaplatos
```

### Ejemplo

Mesón de granito de 3 ml con fondo de 65 cm:

```text
Mesón = 3 × 700.000 × 1.0 = 2.100.000
Lavaplatos = 130.000
Total = 2.230.000
```

---

# 6. Tipo 2 — Isla

## 6.1 Uso

Centro de la cocina con acceso por varios lados.

## 6.2 Componentes principales

- Mesón principal.
- Salpicadero bajo de 10 cm.
- Regrueso en el visto.

## 6.3 Componentes opcionales

- Laterales.
- Regrueso adicional definido para isla.

## 6.4 Componente no incluido

- Lavaplatos.

## 6.5 Profundidad válida

- 55 cm a 120 cm.

## 6.6 Fórmula de cálculo

```text
Total Isla = (ML × Precio Base × Multiplicador)
           + (Laterales si aplica)
           + (Regrueso si aplica)
```

Donde:

```text
Laterales = 1.8 × Precio Base × Multiplicador
Regrueso = 0.9 × Precio Base × 1.0
```

## 6.7 Ejemplo

Isla de granito de 2 ml, fondo 80 cm, con laterales y regrueso:

```text
Mesón = 2 × 700.000 × 1.3 = 1.820.000
Laterales = 1.8 × 700.000 × 1.3 = 1.638.000
Regrueso = 0.9 × 700.000 × 1.0 = 630.000
Total = 4.088.000
```

---

# 7. Tipo 3 — Barra

## 7.1 Uso

Superficie pegada a pared con profundidad reducida o variable.

## 7.2 Componentes incluidos

- Mesón principal.
- Salpicadero bajo de 10 cm.
- Regrueso en el visto.

## 7.3 Opcionales

- Lateral con altura variable.
- Salpicadero alto.

## 7.4 Componente no incluido

- Lavaplatos.

## 7.5 Profundidad válida

- 35 cm a 120 cm.

## 7.6 Regla de barra angosta

Cuando el fondo está entre **35 y 45 cm**, se utiliza el precio especial de barra angosta del material y multiplicador 1.0.

## 7.7 Altura lateral permitida

- 0 cm.
- 90 cm.
- 100 cm.
- 110 cm.

## 7.8 Fórmula de cálculo

```text
Total Barra = (ML × Precio Base × Multiplicador)
            + ((Altura lateral / 100) × Precio Base × Multiplicador)
            + Salpicadero Alto si aplica
```

## 7.9 Ejemplo

Barra de granito de 1.5 ml, fondo 40 cm, lateral de 90 cm:

```text
Mesón = 1.5 × 490.000 × 1.0 = 735.000
Lateral = 0.9 × 490.000 × 1.0 = 441.000
Total = 1.176.000
```

---

# 8. Componentes adicionales

## 8.1 Lavaplatos

| Campo | Valor |
| --- | --- |
| Precio | $130.000 COP |
| Incluido en | Mesón estándar |
| No incluido en | Isla y barra |
| Especificación | 45 × 37 cm, pegado al mesón |

## 8.2 Salpicadero bajo

| Campo | Valor |
| --- | --- |
| Altura | 10 cm |
| Incluido en | Todos los tipos |
| Regla | Se reemplaza si se selecciona salpicadero alto |

## 8.3 Salpicadero alto

| Campo | Valor |
| --- | --- |
| Precio | Duplica el cobro del tramo asociado |
| Disponible en | Mesón estándar y barra |
| No disponible en | Isla |

### Fórmula

```text
Precio Salpicadero Alto = ML × Precio Base × Multiplicador
```

### Ejemplo

Mesón granito de 2 ml, fondo 70 cm, con salpicadero alto:

```text
Mesón = 2 × 700.000 × 1.3 = 1.820.000
Salpicadero alto = 2 × 700.000 × 1.3 = 1.820.000
Lavaplatos = 130.000
Total = 3.770.000
```

## 8.4 Regrueso

### Regla general

- Incluido visualmente en todos los tipos.
- En isla puede existir un cobro adicional normalizado como **0.9 ml**.

## 8.5 Laterales de isla

| Campo | Valor |
| --- | --- |
| Metraje fijo | 1.8 ml |
| Aplicación | Opcional en isla |
| Fórmula | 1.8 × Precio Base × Multiplicador |

## 8.6 Altura lateral de barra

| Altura | Conversión para cobro |
| --- | ---: |
| 0 cm | 0.0 ml |
| 90 cm | 0.9 ml |
| 100 cm | 1.0 ml |
| 110 cm | 1.1 ml |

---

# 9. Comparativa de materiales

| Material | Precio estándar | Barra angosta | Observación |
| --- | ---: | ---: | --- |
| Granito | $700.000/ml | $490.000/ml | Base económico |
| Cuarzo | $850.000/ml | $600.000/ml | Mayor valor que granito |
| Sinterizado | $1.200.000/ml | $1.000.000/ml | Opción de mayor precio |

---

# 10. Transporte e imprevistos

## 10.1 Valor por defecto

- **$150.000 COP**.

## 10.2 Aplicación

- Opcional.
- Se suma al subtotal de mesones cuando se incluye.

## 10.3 Fórmula

```text
Total General = Subtotal Mesones + Transporte
```

### Ejemplo

```text
Mesón = 2.275.000
Transporte = 150.000
Total = 2.425.000
```

---

# 11. Casos de uso reales normalizados

## Caso 1 — Mesón estándar de granito

```text
Tipo: Mesón estándar
Material: Granito
Metraje: 2.5 ml
Fondo: 65 cm
Salpicadero alto: No
Transporte: No

Mesón = 2.5 × 700.000 × 1.0 = 1.750.000
Lavaplatos = 130.000
Total = 1.880.000
```

## Caso 2 — Isla premium en sinterizado

```text
Tipo: Isla
Material: Sinterizado
Metraje: 2.0 ml
Fondo: 80 cm
Laterales: Sí
Regrueso: Sí
Transporte: Sí

Mesón = 3.120.000
Laterales = 2.808.000
Regrueso = 1.080.000
Transporte = 150.000
Total = 7.158.000
```

## Caso 3 — Barra angosta en granito

```text
Tipo: Barra
Material: Granito
Metraje: 1.5 ml
Fondo: 40 cm
Lateral: 90 cm
Transporte: No

Mesón = 735.000
Lateral = 441.000
Total = 1.176.000
```

## Caso 4 — Mesón de cuarzo con salpicadero alto

```text
Tipo: Mesón estándar
Material: Cuarzo
Metraje: 3.0 ml
Fondo: 75 cm
Salpicadero alto: Sí
Transporte: Sí

Mesón = 3.315.000
Salpicadero alto = 3.315.000
Lavaplatos = 130.000
Transporte = 150.000
Total = 6.910.000
```

## Caso 5 — Mix de mesones

```text
Mesón granito = 1.530.000
Isla cuarzo = 3.945.000 según fuente original
Barra sinterizado = 2.100.000
Transporte = 150.000
Total = 7.725.000 según fuente original
```

## Observación documental crítica

En el caso mixto, el subtotal de isla de cuarzo presentado en la fuente requiere revisión matemática, porque la suma de los componentes descritos da un valor distinto al subtotal informado. Este punto queda pendiente de validación.

---

# 12. Estructura documental del ítem de cotización

La fuente propone una estructura de ítem que permite cotizar uno o más mesones en una misma configuración.

## 12.1 Campos generales

- Número de ítem.
- Tipo de ítem.
- Descripción.
- Cantidad.
- Precio unitario.
- Precio total.

## 12.2 Configuración especializada

Cada mesón puede incluir:

- Material.
- Tipo.
- Metros lineales.
- Fondo.
- Precio por ml.
- Inclusión de laterales.
- Inclusión de regrueso.
- Altura lateral.
- Inclusión de salpicadero alto.
- Subtotales desagregados.
- Total individual.

---

# 13. Validaciones principales

| Campo | Regla |
| --- | --- |
| Metraje | 0.5 ml a 10 ml |
| Fondo barra | 35 cm a 120 cm |
| Fondo mesón e isla | 55 cm a 120 cm |
| Altura lateral barra | 0, 90, 100 o 110 cm |
| Materiales válidos | Granito, Cuarzo, Sinterizado |

---

# 14. Comparativa de tipos de mesón

| Aspecto | Mesón estándar | Isla | Barra |
| --- | --- | --- | --- |
| Ubicación | Pared | Centro | Pared |
| Profundidad | 55-120 cm | 55-120 cm | 35-120 cm |
| Lavaplatos | Incluido | No | No |
| Laterales | No | Opcional | Opcional mediante altura lateral |
| Regrueso | Incluido | Opcional con cobro específico | Incluido |
| Salpicadero alto | Opcional | No | Opcional |
| Uso típico | Cocina principal | Centro de cocina | Desayuno o apoyo |

---

# 15. Flujo de cotización con Mesones

1. Crear cotización.
2. Agregar ítem Mesones.
3. Seleccionar tipo.
4. Seleccionar material.
5. Ingresar metraje.
6. Ingresar profundidad.
7. Calcular multiplicador.
8. Seleccionar opcionales según tipo.
9. Incluir transporte si aplica.
10. Calcular precio automático.
11. Agregar más mesones si aplica.
12. Calcular subtotal general.
13. Aplicar descuento si existe.
14. Generar total final.
15. Enviar cotización.

---

# 16. Ejemplo completo de cotización normalizada

## Cliente

- Patricia González.
- Proyecto: Remodelación Cocina Integral.

## Ítem 1 — Mesón estándar granito

```text
Material: Granito
Metraje: 2.5 ml
Fondo: 75 cm
Multiplicador: 1.3
Mesón: 2.275.000
Lavaplatos: 130.000
Subtotal: 2.405.000
```

## Ítem 2 — Isla cuarzo

```text
Material: Cuarzo
Metraje: 1.5 ml
Fondo: 80 cm
Multiplicador: 1.3
Mesón: 1.657.500
Laterales: 1.989.000
Regrueso: 765.000
Subtotal: 4.411.500
```

## Ítem 3 — Barra sinterizado

```text
Material: Sinterizado
Metraje: 1.2 ml
Fondo: 40 cm
Barra: 1.200.000
Lateral 90 cm: 900.000
Subtotal: 2.100.000
```

## Total cotización

```text
Subtotal general: 8.916.500
Transporte: 150.000
Descuento 10%: -906.650
Total final: 8.159.850
```

---

# 17. Puntos pendientes de resolución

1. Confirmar si la categoría debe llamarse definitivamente **Mesones** o mantener el nombre comercial **Mesones con Granito**.
2. Revisar la consistencia entre el nombre de la categoría y los tres materiales disponibles.
3. Confirmar que el lavaplatos siempre se cobra como incluido adicional fijo en mesón estándar.
4. Validar si el regrueso de isla se calcula siempre con multiplicador 1.0.
5. Confirmar si laterales de isla siempre equivalen a 1.8 ml.
6. Confirmar si salpicadero alto realmente duplica solo el tramo del mesón y no otros opcionales.
7. Revisar el caso mixto de mesones, cuya isla de cuarzo presenta una suma inconsistente respecto al total informado.
8. Aclarar si los valores de transporte se aplican una vez por cotización o una vez por grupo de mesones.

---

# 18. Cierre documental

Este documento consolida la primera versión profesional de la fuente de verdad funcional para **Mesones**.

Será la base para construir los siguientes documentos de la carpeta:

- Glosario.
- Reglas de negocio.
- Modelo de entradas.
- Modelo de cálculo.
- Validaciones.
- Casos de prueba.
- Riesgos y decisiones.
- Propuesta de contrato futuro.
