# Caso 3: Gestión de pricing y recuperación de descuentos

## Resumen

Identificación y maximización de una fuente de margen adicional en una empresa que actuaba como intermediaria entre proveedores y clientes. Con consultas en SQL se detectaban cada mes los artículos sobre los que se podía pedir descuento al proveedor, y un dashboard permitía seguir dónde se generaba esa gestión.

**Resultado**

- Alrededor de **USD 10.000** de gestión de pricing en un trimestre.
- La facturación aumentó **5 %**.

## El problema

La empresa era intermediaria entre el proveedor y el cliente. Manejaba una lista de casi **10.000 artículos**, y cada cliente podía tener **varios acuerdos comerciales** vigentes.

Se identificó una oportunidad: después de la venta, había artículos sobre los que la empresa podía **solicitar un descuento al proveedor**. La diferencia entre el precio al que se vendió el artículo y el costo final tras ese descuento era una ganancia adicional. Esa oportunidad se identificó y se maximizó.

## Qué construí

| Componente | Qué hace |
| --- | --- |
| Consultas SQL | Descargan todas las ventas del mes y permiten identificar los artículos específicos sobre los que se solicita descuento |
| Rebate de cierre de mes | Se liquida el rebate correspondiente y la variación se cuantifica como **"gestión de pricing"** |
| Dashboard de seguimiento | Muestra mes a mes en qué clientes y en qué artículos se genera más gestión de pricing |

## Metodología

1. **Extracción.** Con SQL se descargaban todas las ventas efectuadas en el mes.
2. **Identificación.** Se seleccionaban los artículos sobre los que correspondía pedir descuento al proveedor.
3. **Solicitud de descuento.** Se pedía el descuento al proveedor para esos artículos específicos.
4. **Rebate de cierre de mes.** Al finalizar el mes se realizaba el rebate y se cuantificaba la variación entre el precio de venta y el costo obtenido.
5. **Seguimiento.** El dashboard permitía ver en qué clientes y artículos se concentraba la gestión.

## Resultados

| Indicador | Valor |
| --- | --- |
| Catálogo de artículos | casi 10.000 |
| Gestión de pricing en un trimestre | ~ USD 10.000 |
| Aumento de la facturación | 5 % |

## Material de ejemplo

Todo el material de esta sección usa **datos ficticios por temas de confidencialidad hacia la empresa**. Recrea el método, no cifras reales: solo los totales del trimestre (~USD 10.000 y 5 %) corresponden al resultado del caso. El desglose por mes, cliente y artículo es inventado, y los clientes y artículos están anonimizados.

## Herramientas

- **SQL** para extracción y análisis de ventas.
- **Dashboard** para seguimiento de la gestión de pricing por cliente y artículo.
