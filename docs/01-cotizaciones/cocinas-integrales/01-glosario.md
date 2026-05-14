# Glosario — Cocinas Integrales

## 1. Propósito

Este documento define el vocabulario funcional mínimo para documentar, revisar y posteriormente implementar la categoría **Cocinas Integrales** sin ambigüedad entre negocio, producto y tecnología.

Las definiciones se apoyan en la fuente normalizada existente y separan conceptos comerciales de interpretaciones funcionales.

---

# 2. Términos principales

## 2.1 Cocina integral

**Clasificación:** Interpretación funcional.

Configuración comercial que agrupa muebles, mesón y componentes complementarios según el tipo de producto seleccionado. Puede incluir muebles superiores, inferiores, módulos especiales, islas, barras, acabados y herrajes.

## 2.2 Tipo de cocina

**Clasificación:** Definido por cliente.

Variante comercial que determina la lógica base de la cotización. Los tipos actualmente documentados son:

- Cocina Completa.
- Solo Muebles Superiores.
- Solo Muebles Inferiores.
- Frente PLL / Frente Pollo.
- Puertas y Tapas.
- Solo Acabados.

## 2.3 Metraje total

**Clasificación:** Definido por cliente.

Cantidad inicial de metros lineales indicada para la cocina antes de aplicar descuentos por módulos especiales.

## 2.4 Metraje resultante

**Clasificación:** Interpretación funcional.

Metraje usado como base de cálculo para muebles lineales y, cuando aplique, para mesón.

```text
Metraje Resultante = Metraje Total - Descuentos de Módulos Especiales
```

## 2.5 Módulo especial

**Clasificación:** Definido por cliente.

Elemento de mayor complejidad o configuración específica que reduce el metraje lineal continuo y puede tener precio propio. Ejemplos:

- Nicho Nevecon.
- Nicho Nevera.
- Alacena Entrepaños.
- Alacena Herraje.
- Torre de Hornos.

## 2.6 Descuento de metraje

**Clasificación:** Definido por cliente.

Cantidad de metros lineales que se resta del metraje total cuando se selecciona un módulo especial.

## 2.7 Precio por metro lineal

**Clasificación:** Definido por cliente.

Valor monetario aplicado por cada metro lineal cotizable de mueble, frente o mesón, según el componente y nivel comercial.

## 2.8 Nivel de cocina

**Clasificación:** Definido por cliente.

Segmento comercial asociado al valor de los muebles lineales. Los niveles actualmente identificados son:

- Standard.
- Premium.
- Deluxe.

## 2.9 Mueble inferior

**Clasificación:** Interpretación funcional.

Componente lineal de almacenamiento ubicado en la parte baja de la cocina. En Cocina Completa se calcula de manera paralela al mueble superior.

## 2.10 Mueble superior

**Clasificación:** Interpretación funcional.

Componente lineal de almacenamiento ubicado en la parte alta de la cocina. En Cocina Completa se calcula de manera paralela al mueble inferior.

## 2.11 Frente PLL / Frente Pollo

**Clasificación:** Definido por cliente.

Frente visible de puertas y cajoneros para cocinas construidas sobre base vaciada en concreto, sin fabricar el mueble completo.

## 2.12 Mesón

**Clasificación:** Definido por cliente.

Cubierta de trabajo asociada a la cocina, cotizable por metro lineal según material y profundidad. Materiales documentados:

- Sinterizado.
- Cuarzo / Quarzone.
- Granito.
- Ninguno.

## 2.13 Profundidad del mesón

**Clasificación:** Definido por cliente.

Medida transversal del mesón que determina si se aplica recargo:

- Hasta 60 cm: sin recargo.
- 61 a 90 cm: +30%.
- 91 a 120 cm: +100%.

## 2.14 Recargo por profundidad

**Clasificación:** Definido por cliente.

Factor multiplicador aplicado sobre el valor base del mesón por exceder la profundidad estándar.

## 2.15 Isla

**Clasificación:** Definido por cliente.

Elemento independiente o complementario de la cocina con mesón propio, dimensiones específicas y posibles regruesos laterales.

## 2.16 Barra

**Clasificación:** Definido por cliente.

Superficie complementaria asociada a la isla o al diseño general, con reglas propias de profundidad, lateral y herraje.

## 2.17 Regrueso

**Clasificación:** Definido por cliente.

Extensión lateral o vertical del mesón que agrega metraje cotizable. Su fórmula exacta aún requiere validación comercial.

## 2.18 Herraje

**Clasificación:** Definido por cliente.

Componente adicional asociado al funcionamiento o fijación del producto. Ejemplos:

- Bisagras.
- Rieles de cajón.
- Manijas.
- Cerraduras.
- Soportes.

## 2.19 Acabado especial

**Clasificación:** Definido por cliente.

Tratamiento, material o mejora estética que puede alterar el precio del producto o convertirse en una categoría independiente.

## 2.20 Costo fijo

**Clasificación:** Definido por cliente.

Cargo adicional configurable que puede aplicar a un ítem o a un proyecto, según decisión pendiente. El valor estándar documentado es de **$600.000 COP**.

## 2.21 Transporte

**Clasificación:** Definido por cliente.

Cargo logístico documentado con valor de referencia de **$600.000 COP**, actualmente marcado como desactivado en cálculos.

## 2.22 Descuento comercial

**Clasificación:** Definido por cliente.

Porcentaje aplicado sobre el subtotal de la cotización. El límite máximo indicado es **50%**.

## 2.23 Subtotal

**Clasificación:** Interpretación funcional.

Suma de muebles, mesón y componentes adicionales antes de descuento.

## 2.24 Total final

**Clasificación:** Interpretación funcional.

Valor resultante después de aplicar el descuento y los ajustes que correspondan según decisiones comerciales vigentes.

---

# 3. Términos que requieren definición posterior

Los siguientes conceptos existen en la fuente, pero requieren cierre en documentos de decisión:

1. Si el precio de los módulos especiales es adicional o está embebido en muebles.
2. Fórmula exacta del metraje cotizable de islas.
3. Fórmula exacta del regrueso en barras.
4. Aplicación del mesón en Frente PLL.
5. Alcance exacto de costos fijos y transporte.

---

# 4. Criterio de uso del glosario

Toda documentación posterior de la categoría deberá usar estos términos de forma consistente. Cuando una regla dependa de un concepto no estabilizado, debe marcarse como **pendiente de validación**.