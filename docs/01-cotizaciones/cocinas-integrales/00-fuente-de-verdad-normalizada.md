# Fuente de Verdad Normalizada — Cocinas Integrales

## 1. Propósito del documento

Este documento transforma la información comercial original entregada por el cliente en una versión **ordenada, profesional y utilizable como base documental del sistema**.

No constituye todavía una especificación técnica definitiva ni una implementación. Su función es:

- Conservar la intención original del cliente.
- Reorganizar la información por conceptos.
- Separar reglas, ejemplos y dudas.
- Preparar el trabajo posterior de reglas de negocio, modelos de cálculo y contratos de software.

---

# 2. Alcance funcional de la categoría

La categoría **Cocinas Integrales** permite construir una cotización a partir de:

1. Tipo de cocina.
2. Metraje lineal total.
3. Selección de módulos especiales.
4. Metraje resultante de muebles y/o mesón.
5. Selección de mesón.
6. Recargos por profundidad del mesón.
7. Configuración de isla, barra y regruesos cuando corresponda.
8. Componentes adicionales.
9. Descuentos.
10. Costos fijos y transporte, según aplique.

---

# 3. Tipos de cocina disponibles

| Tipo | Descripción funcional | Regla base de cálculo |
| --- | --- | --- |
| Cocina Completa | Incluye muebles superiores e inferiores | Se considera doble línea de mueble sobre el metraje aplicable |
| Solo Muebles Superiores | Incluye únicamente gabinetes superiores | Una línea de mueble sobre el metraje total |
| Solo Muebles Inferiores | Incluye únicamente gabinetes inferiores | Una línea de mueble sobre el metraje total |
| Frente PLL / Frente Pollo | Frente fabricado para cocinas vaciadas en concreto, con puertas y cajoneros | Precio lineal especial |
| Puertas y Tapas | Reemplazo o fabricación de frentes, puertas y tapas | Precio especial por pieza |
| Solo Acabados | Acabados especiales independientes | Precio especial según acabado |

## Observación documental

Los tipos **Puertas y Tapas** y **Solo Acabados** aparecen dentro de la fuente de Cocinas Integrales, pero también tienen naturaleza de subcategorías o categorías especializadas. Durante la documentación posterior se debe decidir si:

- Permanecen como opciones internas de Cocinas Integrales.
- Se documentan solo por referencia y se desarrollan de forma independiente en sus carpetas específicas.

---

# 4. Medidas de la cocina

## 4.1 Dato principal de entrada

- **Metraje total:** número expresado en metros lineales.

## 4.2 Rango de referencia informado por el cliente

- Rango típico: entre **1.5 ml** y **6 ml**.

## 4.3 Validaciones generales mencionadas

- Mínimo funcional indicado: **0.5 ml**.
- Máximo funcional indicado: **10 ml**.

## Observación documental

La fuente contiene dos criterios distintos:

- Rango típico comercial: 1.5 ml a 6 ml.
- Rango de validación general: 0.5 ml a 10 ml.

Por ahora se normalizan así:

- **Rango permitido documental:** 0.5 ml a 10 ml.
- **Rango típico comercial:** 1.5 ml a 6 ml.

---

# 5. Módulos especiales y descuentos de metraje

## 5.1 Naturaleza funcional

Los módulos especiales representan muebles de piso a techo o configuraciones especiales que:

- Tienen valor propio informado por el cliente.
- Reducen el metraje lineal utilizado para calcular la parte continua de la cocina.
- Determinan el metraje de referencia para el mesón cuando corresponda.

## 5.2 Tabla normalizada

| Módulo especial | Descuento de metraje | Precio informado |
| --- | ---: | ---: |
| Nicho Nevecon | -1.00 ml | $1.200.000 COP |
| Nicho Nevera | -0.75 ml | $1.100.000 COP |
| Alacena Entrepaños | -0.50 ml | $1.250.000 COP |
| Alacena Herraje | -0.50 ml | $900.000 COP |
| Torre de Hornos | -0.70 ml | $1.350.000 COP |

## 5.3 Fórmula documental de metraje resultante

```text
Metraje Resultante = Metraje Total - Sumatoria de Descuentos por Módulos Especiales
```

## 5.4 Ejemplo base

```text
Metraje Total: 5.0 ml
Módulo especial: Nicho Nevecon (-1.0 ml)
Metraje Resultante: 4.0 ml
```

## Observación documental importante

La fuente presenta una posible contradicción:

- En una sección se indica que estos módulos tienen **precio aparte establecido**.
- En otra sección se menciona que su precio estaría **incluido en muebles**.

Este punto debe tratarse como **pendiente de definición comercial** antes de convertir la documentación en especificación técnica.

---

# 6. Precios base de muebles lineales

## 6.1 Niveles de cocina mencionados

Para cocinas completas se mencionan tres niveles de precio:

| Nivel | Precio por línea de mueble / ml |
| --- | ---: |
| Standard | $900.000 COP |
| Premium | $1.100.000 COP |
| Deluxe | $1.350.000 COP |

## 6.2 Aclaración de nomenclatura

La fuente indica que el valor de **$900.000 COP/ml** corresponde realmente a la línea **Standard**.

---

# 7. Fórmulas base de muebles por tipo de cocina

## 7.1 Cocina Completa

Incluye muebles inferiores y superiores.

```text
Total Muebles = (Metraje Resultante × Precio Mueble Inferior)
              + (Metraje Resultante × Precio Mueble Superior)
```

En su forma simplificada para un mismo nivel de precio:

```text
Total Muebles = Metraje Resultante × Precio por ml × 2
```

### Ejemplo

```text
Metraje: 4.5 ml
Precio Standard: $900.000/ml
Mueble inferior: 4.5 × 900.000 = $4.050.000
Mueble superior: 4.5 × 900.000 = $4.050.000
Total muebles: $8.100.000
```

## 7.2 Solo Muebles Superiores

```text
Total = Metraje Total × Precio por ml
```

## 7.3 Solo Muebles Inferiores

```text
Total = Metraje Total × Precio por ml
```

## 7.4 Frente PLL / Frente Pollo

```text
Total = Metraje Total × $750.000 COP/ml
```

### Definición funcional

Corresponde a frente de puertas y cajoneros para cocinas vaciadas en concreto, donde no se fabrica el mueble completo sino solo el frente visible.

---

# 8. Mesones disponibles

## 8.1 Tipos de material

| Tipo de mesón | Precio base por ml | Descripción funcional |
| --- | ---: | --- |
| Sinterizado | $1.200.000 COP | Material de alta durabilidad |
| Cuarzo / Quarzone | $850.000 COP | Material intermedio |
| Granito | $700.000 COP | Material más económico |
| Ninguno | $0 COP | No se cotiza mesón |

---

# 9. Reglas de aplicación del mesón

## 9.1 Casos donde no se aplica mesón

El mesón no se aplica en:

- Solo Muebles Superiores.
- Puertas y Tapas.

## 9.2 Casos donde sí puede aplicar

El mesón puede aplicarse en:

- Cocina Completa.
- Solo Muebles Inferiores.
- Frente PLL / Frente Pollo, sujeto a validación comercial futura si se requiere.
- Otras configuraciones donde el cliente defina cubierta.

## Observación documental

La fuente marca como habilitadas “todas las demás opciones” diferentes de los casos excluidos. Esa regla se conserva, aunque podrá ajustarse posteriormente en las reglas específicas.

---

# 10. Recargos por profundidad del mesón

## 10.1 Profundidades normalizadas

| Rango de profundidad | Regla de recargo |
| --- | --- |
| Hasta 60 cm | Sin recargo |
| 61 cm a 90 cm | +30% |
| 91 cm a 120 cm | +100% / precio doble |

## 10.2 Fórmulas

### Sin recargo

```text
Precio Final Mesón = Metraje × Precio Base/ml
```

### Recargo 30%

```text
Precio Final Mesón = Precio Base Mesón × 1.30
```

### Recargo doble

```text
Precio Final Mesón = Precio Base Mesón × 2.00
```

---

# 11. Isla de cocina

## 11.1 Datos necesarios según fuente

Para cotizar una isla se requiere definir:

- Material del mesón: granito, quarzone o sinterizado.
- Largo de isla.
- Profundidad.
- Aplicación de recargo por profundidad.
- Regrueso a un lado o ambos lados.

## 11.2 Regla de regrueso informada

Cuando existe regrueso:

- Se adicionan **90 cm al largo de mesón por cada lado**.
- Se adicionan **60 cm de regrueso por lateral**.

## 11.3 Ejemplo del cliente

Isla de 2.0 m de largo, con regrueso a ambos lados, profundidad de 90 cm, en quarzo:

```text
2.0 m de cubierta
+ 1.80 m de laterales
+ 0.60 m de regrueso
= 4.40 m
```

Luego se aplica recargo de 30%:

```text
Base aproximada: $3.740.000
Recargo 30%: $1.122.000
Total: $4.862.000
```

## Observación documental crítica

La redacción de la fórmula de isla requiere formalización posterior para evitar interpretaciones contradictorias, especialmente en:

- Cómo se agrupan los regruesos.
- Si los 60 cm de regrueso se aplican una sola vez o por lateral.
- Cómo se calcula exactamente el metraje cotizable total.

---

# 12. Barra de isla

## 12.1 Reglas principales

- Si lleva herraje, se adiciona un costo fijo de **$350.000 COP**.
- Para barras de **35 cm a 45 cm**, se cobra el **80%** del costo del metro lineal del material.
- Si la barra supera **50 cm y hasta 60 cm**, se cobra el **100%** del costo del metro lineal del material.
- Si lleva lateral, se suma el alto de la barra por dos como regrueso interno.

## 12.2 Fórmula base informada

```text
Total Barra = (Metraje × Precio Mesón × 0.80)
            + (Lateral × Precio Mesón × 0.80)
            + Herraje
```

## Observación documental

La fuente expresa una regla distinta cuando la barra pasa de 50 cm a 60 cm, por lo que la fórmula general deberá tener dos versiones:

- Versión con factor 0.80.
- Versión con factor 1.00.

---

# 13. Cálculo total general de la cotización

## 13.1 Fórmula comercial general entregada

```text
Subtotal = Muebles Lineales + Mesón + Otros Componentes
Descuento = Subtotal × (Porcentaje de Descuento / 100)
Total = Subtotal - Descuento
```

## 13.2 Observación sobre impuestos

La fuente documental del cliente no establece IVA dentro de la fórmula final de Cocinas Integrales. Cualquier incorporación de impuestos deberá definirse en un documento de decisiones pendientes o validación comercial posterior.

---

# 14. Componentes adicionales

## 14.1 Herrajes

Categorías disponibles informadas:

- Bisagras.
- Rieles de cajón.
- Manijas / tiradores.
- Cerraduras.
- Soportes.

Cada herraje debe tener:

- Nombre.
- Descripción.
- Opciones disponibles.
- Precio unitario.

## 14.2 Acabados especiales

Datos mencionados:

- Tipo de madera o material.
- Color.
- Acabado: brillante, pintado al poliuretano, mate, entre otros.
- Foto de referencia.

---

# 15. Costos fijos

## 15.1 Definición funcional

Los costos fijos son cargos adicionales que pueden aplicar a ciertos ítems de la cotización.

Ejemplos entregados:

- Instalación.
- Transporte.
- Mano de obra especial.
- Diseño.
- Otros servicios.

## 15.2 Valor por defecto informado

- Costo fijo estándar: **$600.000 COP**.

## 15.3 Fórmula referencial

```text
Precio Item = Precio Base + Costo Fijo
```

---

# 16. Transporte y otros costos

## 16.1 Transporte

- Valor estándar mencionado: **$600.000 COP**.
- Estado actual indicado por el cliente: **$0**, desactivado en cálculos.

## 16.2 Otros conceptos

- Instalación: incluida con la cocina.
- Diseño 3D: incluido con la cocina; si se vende por separado, costo de **$350.000 COP**.
- Asesoría: gratuita si se adquiere cocina o si se paga diseño.
- Garantía extendida: no existe actualmente, pero se podría analizar a futuro.

---

# 17. Resumen de precios base

| Componente | Precio | Unidad |
| --- | ---: | --- |
| Mueble inferior Standard | $900.000 COP | Por metro lineal |
| Mueble superior Standard | $900.000 COP | Por metro lineal |
| Cocina Premium | $1.100.000 COP | Por metro lineal |
| Cocina Deluxe | $1.350.000 COP | Por metro lineal |
| Frente PLL / Frente Pollo | $750.000 COP | Por metro lineal |
| Mesón Sinterizado | $1.200.000 COP | Por metro lineal |
| Mesón Cuarzo / Quarzone | $850.000 COP | Por metro lineal |
| Mesón Granito | $700.000 COP | Por metro lineal |
| Costo fijo estándar | $600.000 COP | Según aplicación |
| Transporte | $600.000 COP | Por cotización si aplica |
| Diseño 3D separado | $350.000 COP | Servicio individual |

---

# 18. Flujo completo de cotización

1. Seleccionar tipo de cocina.
2. Ingresar metraje total.
3. Seleccionar módulos especiales opcionales.
4. Calcular metraje resultante.
5. Seleccionar tipo de mesón.
6. Seleccionar recargo de mesón si aplica.
7. Seleccionar herrajes y acabados.
8. Calcular subtotal.
9. Aplicar descuento si existe.
10. Generar total final.
11. Agregar a cotización.
12. Generar PDF y enviar.

---

# 19. Reglas de redondeo y descuentos

## 19.1 Redondeo

- Todos los precios finales se redondean a números enteros.
- No se usan decimales en cotizaciones finales.

## 19.2 Descuentos

- Descuento máximo indicado: **50%**, configurable.

---

# 20. Campos configurables por ítem

La fuente indica que un ítem de cotización puede considerar:

- Descripción personalizada.
- Cantidad.
- Precio unitario.
- Precio total.
- Incluye costos fijos: sí / no.
- Monto de costos fijos.
- Configuración de cocina en formato estructurado.
- Selecciones de herrajes en formato estructurado.
- Configuración de mesón en formato estructurado.

---

# 21. Ejemplo práctico final del cliente

## Escenario

- Cliente: Juan Pérez.
- Proyecto: Cocina Integral para Casa Nueva.
- Tipo: Cocina Standard.
- Metraje: 4.5 ml.
- Módulos: Nicho Nevecon y Torre de Hornos.
- Mesón: Sinterizado sin recargo.
- Descuento: 5%.

## Cálculo normalizado

### 1. Metraje resultante

```text
4.5 - 1.0 - 0.7 = 2.8 ml
```

### 2. Muebles

```text
2.8 × 900.000 × 2 = $5.040.000
```

### 3. Mesón

```text
2.8 × 1.200.000 = $3.360.000
```

### 4. Subtotal

```text
$5.040.000 + $3.360.000 = $8.400.000
```

### 5. Descuento

```text
5% de $8.400.000 = $420.000
```

### 6. Total final

```text
$8.400.000 - $420.000 = $7.980.000
```

---

# 22. Puertas, tapas y acabados relacionados

## 22.1 Puertas y tapas

| Concepto | Precio |
| --- | ---: |
| Puertas superiores hasta 70 cm | $120.000 COP |
| Puertas superiores hasta 90 cm | $150.000 COP |
| Puertas superiores mayores a 100 cm | $180.000 COP |
| Puertas inferiores | $150.000 COP |
| Puertas de alacena | $180.000 COP |
| Tapas de cajón | $90.000 COP |
| Tapas pequeñas y demás | $45.000 COP |

## 22.2 Acabados especiales vinculados

| Concepto | Precio / Regla |
| --- | --- |
| Luz LED | $220.000 COP por metro lineal |
| Puerta de vidrio ahumado con marco de aluminio negro | $1.200.000 COP por m² |
| Bisagras adicionales si altura > 80 cm | +1 par a $15.000 COP/par |
| Bisagras adicionales si altura > 140 cm | +2 pares a $15.000 COP/par |

## 22.3 Pintado de puertas alto brillo

| Concepto | Precio |
| --- | ---: |
| Puertas superiores | $120.000 COP |
| Puertas inferiores | $150.000 COP |
| Puertas de alacena | $250.000 COP |
| Tapas de cajón | $90.000 COP |
| Tapa especiero | $100.000 COP |
| Tapa pequeña o gola | $45.000 COP |

---

# 23. Puntos pendientes de resolución

La fuente de verdad queda normalizada, pero se identifican temas que deberán tratarse en documentos posteriores:

1. Confirmar si los módulos especiales tienen precio adicional o están incluidos en muebles.
2. Formalizar de forma exacta la fórmula de islas.
3. Formalizar la fórmula de barras según profundidad.
4. Definir si Frente PLL admite mesón bajo todas las circunstancias.
5. Confirmar si transporte se mantiene desactivado por defecto.
6. Confirmar si costo fijo de $600.000 es por ítem o por proyecto según contexto.
7. Determinar si impuestos forman o no parte de la categoría.
8. Separar claramente qué pertenece a Cocinas Integrales y qué debe pasar a Acabados Especiales o Puertas.

---

# 24. Cierre documental

Este documento consolida la primera versión profesional de la fuente de verdad funcional para **Cocinas Integrales**.

Será la base para construir los siguientes documentos de la carpeta:

- Glosario.
- Reglas de negocio.
- Modelo de entradas.
- Modelo de cálculo.
- Validaciones.
- Casos de prueba.
- Riesgos y decisiones.
