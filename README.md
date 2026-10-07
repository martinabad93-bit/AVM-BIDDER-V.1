# AVM-BIDDER PLUS V1.1

## Objetivo
V1.1 prioriza funcionalidad, velocidad y sincronización sobre estética. Mantiene el formato general de V1.0, pero incorpora un flujo rápido tipo Wizard y una capa centralizada para que la selección del vehículo cargue automáticamente sus parámetros.

## Flujo
1. **Vehículo**: Marca → Modelo → Año → Serie/registro exacto, o búsqueda rápida.
2. **Costos**: se precargan los costos fijos y solo se editan los variables.
3. **Puja**: se introduce la puja y, opcionalmente, precio de venta y objetivos.
4. **Decisión**: muestra Bid Ideal, Max Bid, Bid Riesgo y Landed.

## Base de datos
Se utiliza el CSV `Base de Datos Valores Vehiculos 2026 - 2027.csv` incluido en el proyecto.
La aplicación carga todos los registros disponibles del CSV y normaliza:
- Marca
- Modelo
- Año
- País/Origen
- Serie
- Tipo de vehículo
- Combustible
- Cilindros
- CC
- Pasajeros
- Puertas
- Tracción
- Cabinas
- Peso de carga
- Ejes
- Valor AVM

La tracción se normaliza para búsqueda: AWD/4WD/4X4 se consideran familia AWD; FWD/4X2/2WD familia FWD; RWD se mantiene separado.

## Parámetros precargados
- Broker: US$250 hasta US$15,000.
- Documentación y logística origen: US$675.
- Flete marítimo: US$910.
- Despacho RD: US$465.
- Reparación base: US$950, editable.
- Honorarios: US$0 por defecto, editable.
- Normativa 03-25: RD$0 por defecto, editable.
- PP: RD$2,000.
- Endoso/Gestión: RD$5,000.

Auction Fee e Inland son variables de la operación. Si se suministra un valor manual, debe respetarse.

## Cálculos
FOB Miami excluye flete marítimo y despacho RD.
Landed incluye FOB + flete + aduanas/impuestos + despacho RD.
La interfaz muestra margen y ROI cuando existe precio de venta.

## Importante sobre impuestos
Esta versión deja Aduanas en US$0 hasta integrar en este proyecto la fórmula fiscal validada de NEXT. No se inventa una fórmula fiscal nueva.

## Nueva consulta
La acción Nueva consulta limpia la operación actual para evitar arrastrar precio de venta u otros datos de una consulta anterior.

## Compatibilidad
Proyecto independiente. No modifica NEXT GB V2.5 ni AVM-BIDDER PLUS V1.0.

## Nota de arquitectura
La capa `AVM_SYNC` centraliza la lectura y normalización de la base de datos. `AVM_DEFAULTS` centraliza parámetros fijos. El objetivo es que futuras funciones manuales, AI EDOM PILOT y el Bidder utilicen la misma fuente de verdad.
