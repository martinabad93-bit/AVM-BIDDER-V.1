# AVM-BIDDER PLUS V1.3

Versión de corrección funcional autorizada.

## Objetivo
AVM no replica NEXT GB. Usa la misma base de vehículos y la lógica determinística de NEXT como referencia, pero reduce el flujo a:

**Vehículo → Puja → Costo total → Rentabilidad → Max Bid**

## Correcciones principales
- Un solo flujo de selección y un único registro de vehículo.
- `Valor` de la base se trata exclusivamente como **Valor Tabla Aduanas**.
- El valor de compra/puja es independiente.
- El precio de venta/mercado es independiente.
- Se carga automáticamente el valor de tabla al seleccionar el vehículo.
- Aduanas y placa se calculan automáticamente usando la lógica determinística de NEXT disponible en la versión de referencia.
- Auction Fee se calcula con la tabla Copart/IAAI incorporada en NEXT para Online/Live.
- El costo total se actualiza en vivo.
- Se calcula margen, ROI, rentabilidad y Max Bid mediante búsqueda iterativa considerando que el Auction Fee cambia con la puja.
- El Max Bid respeta el margen mínimo y ROI objetivo configurados.

## Valores de referencia
- Documentación + logística origen: US$675
- Reparación Miami: US$950
- Broker: US$250
- Flete: US$910
- Paquete despacho RD: US$465
- Tasa inicial: RD$60/USD
- ROI objetivo inicial: 15%

## Lógica aduanal sincronizada
La base seleccionada aporta el Valor Tabla Aduanas. Sobre esa base se conserva la lógica de NEXT: flete, seguro 2%, gravamen según origen, ITBIS 18%, cargos DGA, primera placa 17%, CO2 2% y RD$3,000 de emisiones. Son estimaciones referenciales, no liquidaciones oficiales de DGA.

## Nota
La versión prioriza funcionalidad y velocidad sobre rediseño visual. NEXT GB V2.5 no se modifica.
