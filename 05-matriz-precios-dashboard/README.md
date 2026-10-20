# Caso 5: Matriz de precios y dashboard de facturación

## Resumen

Matriz de servicios de laboratorio con tarifa, costo, margen, indicador por rango, referencias de precio y desviación frente a la tarifa, más un dashboard de facturación de 4 hospitales por mes y por especialidad.

## Qué es real y qué es inventado

| Dato | Origen |
| --- | --- |
| Nombre de los exámenes y su tarifa | **Real.** Tomados del cotizador público de [Elite Lab](https://www.elitelab.ec/cotizador.html), consultado el 19 de octubre de 2026. Es una muestra de 59 exámenes, no el catálogo completo. |
| Costos | Inventados |
| Referencias de precio 1, 2 y 3 | Inventadas |
| Hospitales, especialidades y facturación del dashboard | Inventados. Los hospitales no existen. |

## Matriz de precios

Hoja `Matriz` de [`matriz_precios_laboratorio.xlsx`](matriz_precios_laboratorio.xlsx):

| Columna | Qué contiene |
| --- | --- |
| Nombre del servicio | Examen de laboratorio |
| Tarifa | Precio del cotizador (real) |
| Costo | Costo inventado |
| Margen | `(Tarifa - Costo) / Tarifa`, entre 12 % y 74 % |
| Indicador de margen | "Margen entre el 10% y 30%", "entre el 30% y 50%", "entre el 50% y 70%" o "mayor al 70%" |
| Referencia 1, 2 y 3 | Tres precios de referencia al lado de la tarifa |
| Promedio de referencias | Promedio de las tres referencias |
| Desviación del promedio vs. tarifa | `(Promedio de referencias - Tarifa) / Tarifa`. Positivo: las referencias cobran más que la tarifa; negativo: cobran menos |

Resultado de la muestra: 21 servicios con margen entre 10 % y 30 %, 20 entre 30 % y 50 %, 15 entre 50 % y 70 %, y 3 por encima de 70 %.

## Archivo de Excel

| Hoja | Contenido |
| --- | --- |
| `Leeme` | Qué es real y qué es inventado, fórmulas y código de colores |
| `Matriz` | La matriz de precios descrita arriba |
| `Facturacion_demo` | Facturación y costo ficticios por hospital, mes y especialidad |
| `Dashboard_datos` | Tablas con fórmulas que alimentan el dashboard |

Texto azul: dato de entrada. Texto negro: fórmula. Texto verde: fórmula que toma datos de otra hoja.

## Herramientas

Excel (fórmulas, formato condicional) y Python para generar el dashboard.
