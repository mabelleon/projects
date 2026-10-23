# Presupuesto vs. real y flujo de caja a 12 meses

## Resumen

Modelo en Excel que compara lo presupuestado con lo real durante seis meses, explica **por qué** cambió la utilidad (volumen, precio o costos) y proyecta el flujo de caja de los seis meses siguientes en tres escenarios, con alerta cuando la caja cae bajo un mínimo definido.

**Resultados del caso de ejemplo (datos ficticios)**

- De enero a junio los ingresos quedaron USD 20.225 (3,7 %) bajo el presupuesto; la mayor parte, USD 15.000, se explica por menor volumen y USD 5.225 por menor precio.
- La utilidad operativa del semestre fue USD 23.020 frente a USD 54.000 presupuestados (−57 %), porque a la caída de ingresos se sumaron gastos fijos por encima de lo previsto.
- Proyección a diciembre: caja de USD 151.695 (optimista), USD 107.816 (base) y USD 61.492 (pesimista).
- Solo el escenario pesimista activa la alerta de caja mínima (USD 65.000), en noviembre y diciembre.

## El problema

El presupuesto anual se revisa tarde y casi siempre solo muestra «cuánto nos desviamos», no por qué. Además, una utilidad positiva no garantiza caja: si los cobros se retrasan, la caja puede caer aunque el negocio sea rentable.

## Qué construí

| Hoja | Contenido |
| --- | --- |
| `Leeme` | Qué es el archivo, la lógica de la proyección y el código de colores |
| `Supuestos` | Caja inicial, caja mínima, cobranza y tabla de escenarios (única fuente de parámetros) |
| `Datos` | Tabla plana mes a mes con presupuesto y real; formato apto para conectar a Power BI |
| `Presupuesto_vs_Real` | Variación de ingresos separada en efecto volumen y efecto precio, y variación de utilidad por mes |
| `Flujo_Base`, `Flujo_Optimista`, `Flujo_Pesimista` | 6 meses reales + 6 proyectados: ingresos, costos, cobros, pagos, caja final y estado |
| `Resumen` | Comparación de los tres escenarios contra el presupuesto anual y gráfico de la caja mensual |

## Metodología

1. **Variación de ingresos.** Efecto volumen = (volumen real − volumen ppto) × precio ppto. Efecto precio = (precio real − precio ppto) × volumen real. Los dos suman exactamente la variación; una columna de chequeo lo verifica.
2. **Utilidad real vs. presupuesto.** Ingresos − costo variable − gastos fijos (personal, arriendo y otros), mes a mes.
3. **Proyección Jul–Dic (rolling forecast).** Parte del promedio de los últimos tres meses reales y aplica los parámetros del escenario: crecimiento mensual del volumen, variación del precio y del costo variable unitario.
4. **Cobros y pagos.** Un porcentaje de cada venta se cobra en el mismo mes y el resto el mes siguiente; los costos se pagan en el mismo mes. Enero incluye las cuentas por cobrar iniciales.
5. **Caja y alerta.** Caja final = caja anterior + cobros − pagos. Si queda bajo la caja mínima, el mes se marca `ALERTA`.

| Parámetro (Jul–Dic) | Base | Optimista | Pesimista |
| --- | --- | --- | --- |
| Crecimiento mensual del volumen | 1,0 % | 2,5 % | −1,0 % |
| Variación del precio | 0 % | +3 % | −2 % |
| Variación del costo variable unitario | 0 % | −2 % | +4 % |
| Cobro en el mismo mes | 60 % | 70 % | 45 % |

## Resultados

| Indicador (USD) | Presupuesto | Base | Optimista | Pesimista |
| --- | --- | --- | --- | --- |
| Ingresos del año | 1.080.000 | 1.054.167 | 1.099.776 | 1.008.073 |
| Utilidad operativa del año | 108.000 | 48.334 | 86.514 | 9.136 |
| Caja final en diciembre | — | 107.816 | 151.695 | 61.492 |
| Meses en alerta | — | 0 | 0 | 2 |

La utilidad anual queda bajo el presupuesto incluso en el escenario optimista, porque el primer semestre ya acumuló una brecha. En el pesimista, la caja baja por la combinación de menor volumen, menor precio, mayor costo y cobros más lentos.

## Material de ejemplo

Todo el material de esta sección usa **datos ficticios**. Recrea el método, no cifras reales ni de ningún empleador. El sector (unidad de servicios de un centro de salud) y el año son ilustrativos.

[`presupuesto_flujo_demo.xlsx`](presupuesto_flujo_demo.xlsx) contiene 8 hojas con 664 fórmulas, sin errores tras recalcular. Las celdas azules con fondo amarillo de `Supuestos` y `Datos` son las que se pueden editar.

**Limitaciones:** el flujo no incluye impuestos, inversiones ni financiamiento; los costos fijos proyectados repiten el promedio de los últimos tres meses; la hoja `Datos` está preparada para Power BI, pero este repositorio no incluye un archivo de Power BI.

## Herramientas

Excel (fórmulas, escenarios, gráficos). Power BI como siguiente paso sobre la hoja `Datos`.
