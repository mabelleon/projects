# Punto de equilibrio y sensibilidad de precios

## Resumen

Modelo en Excel que responde dos preguntas sobre un servicio de salud: **cuántos servicios hay que vender para cubrir los costos** y **qué pasa con la utilidad si se sube o se baja el precio**. Combina el análisis de punto de equilibrio con una sensibilidad de precio basada en la elasticidad de la demanda.

**Resultados del caso de ejemplo (datos ficticios)**

- Punto de equilibrio: ~507 estudios al mes (USD 60.800 de ingresos), frente a 800 estudios actuales.
- Margen de seguridad: 37 %.
- Utilidad operativa actual: USD 22.000 al mes.
- Con elasticidad 1,5 la utilidad es casi plana entre +5 % y +25 % de precio (máximo cerca de USD 138). Subir el precio aporta poco y reduce volumen: la decisión depende de qué tan confiable sea la elasticidad.

## El problema

Antes de ajustar un precio, la gerencia necesita saber cuánto margen tiene el servicio y cuánto volumen puede perder sin dejar de ser rentable. Un precio más alto mejora el margen por unidad pero reduce las ventas; el efecto neto depende de la elasticidad.

## Qué construí

Un libro de Excel con todas las cifras calculadas por fórmula a partir de una hoja de supuestos.

| Hoja | Contenido |
| --- | --- |
| `Leeme` | Qué es el archivo, el modelo de demanda y el código de colores |
| `Supuestos` | Precio, costo variable, costos fijos, volumen, elasticidad y paso de variación (únicas celdas editables) |
| `Equilibrio` | Margen de contribución, punto de equilibrio en unidades e ingresos, margen de seguridad y gráfico de ingresos vs. costos totales |
| `Sensibilidad` | Utilidad con precios de -20 % a +30 %, precio de mayor utilidad y precio óptimo teórico |
| `Elasticidad` | Tabla de dos entradas: utilidad según variación de precio y elasticidad (0,5 a 2,5) |

## Metodología

1. **Margen de contribución** = precio − costo variable unitario.
2. **Punto de equilibrio** = costos fijos ÷ margen de contribución unitario; en ingresos, multiplicado por el precio.
3. **Margen de seguridad** = (volumen actual − punto de equilibrio) ÷ volumen actual.
4. **Demanda con elasticidad constante:** Q = Q0 × (P / P0)^(−e).
5. **Utilidad por escenario** = Q × margen de contribución − costos fijos, para cada variación de precio.
6. **Precio óptimo teórico** = e ÷ (e − 1) × costo variable (válido si e > 1). Con e = 1,5 y costo variable de USD 45 da USD 135, consistente con la grilla.

## Resultados

| Indicador | Valor |
| --- | --- |
| Margen de contribución unitario | USD 75 (62,5 %) |
| Punto de equilibrio | ~507 estudios/mes |
| Margen de seguridad | 37 % |
| Utilidad actual | USD 22.000/mes |
| Precio de mayor utilidad en la grilla | USD 138 (+15 %) |
| Mejora frente a la utilidad actual | ~USD 330/mes |

La lectura útil no es el máximo, sino la forma: con elasticidad 0,5 conviene subir el precio con claridad; con 2,0 o más conviene bajarlo. La tabla de `Elasticidad` muestra ese cambio de signo.

## Material de ejemplo

Todo el material de esta sección usa **datos ficticios**. Recrea el método, no cifras reales ni de ningún empleador. El sector (servicio de imagen en un centro de salud) es ilustrativo.

[`equilibrio_demo.xlsx`](equilibrio_demo.xlsx) contiene 5 hojas con fórmulas (221 en total, sin errores tras recalcular). Las celdas azules con fondo amarillo de `Supuestos` son las que se pueden cambiar.

**Limitaciones:** la elasticidad es un supuesto, no se estima a partir de datos; no se modelan capacidad, competencia ni cambios en los costos fijos.

## Herramientas

Excel (fórmulas, tablas de dos entradas, gráficos).
