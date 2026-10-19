# Caso 1: Estandarización de tarifarios

## Resumen

Unifiqué 4 tarifarios con servicios en común en una sola matriz que cruza costos, márgenes, precios de mercado y desviaciones, y definí los protocolos de la posición de Pricing en una institución de salud en Ecuador.

**Resultado:** la facturación aumentó aproximadamente 20 % y se pudo facturar y prestar el servicio en cualquier sede.

## El problema

Se manejaban 4 tarifarios independientes que compartían varios servicios similares. Los precios estaban desactualizados y un mismo servicio costaba distinto según la sede, así que los pacientes iban a facturar a la sede donde salía más barato.

## Qué construí

Una matriz única que reemplazó los 4 tarifarios. Cada servicio aparece una sola vez, con su costo, su margen, el precio de mercado y la desviación entre ambos.

| Componente de la matriz | Qué permite ver |
| --- | --- |
| Costo del servicio | Base para calcular el margen |
| Margen | Rentabilidad por servicio |
| Pricing del mercado | Referencia externa de comparación |
| Desviación | Dónde el precio se aleja del mercado o del margen esperado |

Se unificaron los servicios de los 4 tarifarios en una sola base: la matriz final cubrió aproximadamente 2000 servicios. Con el criterio de Pareto del 80 % se corrigieron los valores de unos 500 servicios y se calculó su costo adecuado para seguir su margen. La matriz se compartía con la alta gerencia y el departamento de finanzas.

## Protocolos de Pricing

Además de la matriz, establecí los protocolos para la posición de Pricing: cómo se fija, revisa y actualiza un precio.

- Servicio nuevo: se costeaba junto con finanzas mientras se investigaba el precio de mercado.
- Aprobaciones en orden: subdirector técnico y gerente del hospital, luego gerencia de marketing y finanzas.
- Con las aprobaciones, se creaba el servicio en los sistemas y se activaba.
- Seguimiento del margen de cada servicio sobre la matriz compartida con gerencia y finanzas.

## Herramientas y metodología

Excel para el costeo y la matriz de precios; Power BI para una matriz interactiva conectada a la facturación del hospital.

Metodología: consolidación de servicios comunes en una sola fuente de datos, comparación costo vs. mercado, análisis de Pareto y análisis de desviaciones.

## Resultados

| Indicador | Valor |
| --- | --- |
| Tarifarios unificados | 4 → 1 |
| Servicios cubiertos por la matriz | ~2000 |
| Servicios con valor corregido (Pareto 80 %) | ~500 |
| Eficiencia operativa | Facturación y servicio disponibles en cualquier sede habilitada |
| Aumento de la facturación | ~20 % |

## Material de ejemplo

Pendiente: matriz demo con datos ficticios en esta carpeta.
