# AVM-BIDDER PLUS V1.4

Corrección funcional autorizada.

## Correcciones V1.4
- Dark Mode robusto con persistencia local.
- Al seleccionar un vehículo se calcula inmediatamente Aduanas + Emisión de Placa.
- Motor de Aduanas alineado con la función `calc()` de NEXT GB: CIF = valor tabla + flete + seguro; arancel 10% por defecto sin tratado; ITBIS 18%; cargos fijos DGA 8,912.44 + 258.26 + 5,713.61 RD$; primera placa 17%; CO2 2% + RD$3,000.
- Seguro DGA y gastos adicionales quedan en 0 por defecto, igual que NEXT.
- `Valor` de la DB sigue siendo exclusivamente **Valor Tabla Aduanas**.
- La puja/compra y el precio de venta siguen separados.
- Se muestra un panel inmediato de Aduanas + Placa al seleccionar el vehículo.

## Fuente validada
La lógica de impuestos se tomó de la función `calc()` del proyecto NEXT GB de referencia. El resultado es estimado y no sustituye una liquidación oficial DGA.
