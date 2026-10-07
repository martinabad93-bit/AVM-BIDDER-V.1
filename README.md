# AVM-BIDDER PLUS V1.2

## Cambio principal
Se elimina la duplicidad de buscadores de vehículo. Ahora existe **un único buscador universal** y una única cadena de selección sincronizada.

### Una sola entrada
La búsqueda acepta:
- Marca + modelo + año + serie/tracción.
- VIN como texto para preparar el cruce (la decodificación VIN externa sigue siendo una integración posterior).
- Lote como texto para la operación.

### Sincronización simultánea
El resultado seleccionado alimenta simultáneamente:
- Marca
- Modelo
- Año
- Serie
- Origen
- Tracción
- Valor AVM
- Especificaciones disponibles
- Campos internos del motor existente

Los selectores Marca → Modelo → Año → Serie son la misma fuente de selección; no son un segundo buscador.

## Datos mostrados
Se cargan desde la misma base NEXT GB 2026–2027:
- Tipo de vehículo
- Marca
- Modelo
- País
- Serie
- Año
- Combustible
- Cilindros
- CC
- Pasajeros
- Puertas
- Tracción
- Cabinas
- Peso de carga
- Ejes
- Valor

## Objetivo
Primero funcionalidad y sincronización; el diseño visual se mantiene solo cuando no perjudica la eficiencia.

## Nota
V1.2 es independiente de NEXT GB y no modifica V1.0.
