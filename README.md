# AVM-BIDDER PLUS — V1.0

Fecha: 2026-10-06

## Estado
Primera versión independiente del núcleo de análisis de puja.

## Base de trabajo
NEXT-AVPRO-BETA V2.5 se utilizó únicamente como fuente de reglas y datos validados. NEXT no se modifica y su interfaz no se copia.

## Incluye
- Light / Dark.
- Flujo Vehículo → Costos → Resultado.
- Entrada manual, VIN y lote.
- VIN mediante NHTSA vPIC cuando hay conexión.
- Cruce inicial con Base de Datos Valores Vehiculos 2026–2027.
- Matching marca + modelo + año; equivalencia inicial AWD=4WD=4X4.
- Costos editables, FOB Miami, Despacho Sin Placa y Landed.
- Puja ideal, máxima y límite de riesgo.
- Margen y ROI.
- Historial local y configuración.
- ZIP destino predeterminado 33132.

## Reglas de cálculo tomadas de NEXT V2.5
FOB Miami = subasta + fees + inland + documentación/logística origen + reparación Miami + broker.

Despacho Sin Placa = FOB Miami + flete + paquete despacho + aduanas/DGA convertido a USD.

Landed = Despacho Sin Placa + reparación RD convertida a USD en este núcleo inicial.

Valores base: Broker US$250, Documentación/logística US$675, Reparación Miami US$950, Flete US$910, Paquete despacho US$465, Honorarios US$0, ZIP destino 33132.

## AVM-BIDDER V1.0
Auction Fee e Inland son manuales hasta integrar fuentes autorizadas.

costos_fijos = Auction Fee + Inland + Documentación + Reparación Miami + Broker + Honorarios + Flete + Despacho + Aduanas/USD + Reparación RD/USD

puja_por_margen = mercado - costos_fijos - margen_mínimo

puja_por_ROI = (mercado - costos_fijos) / (1 + ROI_objetivo/100)

puja_máxima = mínimo(puja_por_margen, puja_por_ROI), limitada a cero.

puja_ideal = puja_máxima × 0.93

límite_riesgo = puja_máxima × 0.98

## Pendiente
- Matching avanzado de trim/serie y selector de coincidencias.
- Auction Fees dinámicos Copart/IAAI mediante fuente autorizada.
- Inland inteligente por ZIP.
- AVM con comparables y escenarios.
- Aduanas validada.
- Emisión de placa.
- Proforma/PDF.
- Integraciones permitidas.
- Pruebas de regresión con operaciones reales.
