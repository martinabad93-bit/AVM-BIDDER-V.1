# AVM-BIDDER PLUS V1.5

Corrección enfocada en la sincronización de DGA y placa dentro de la sección Costos.

## Cambios
- Al seleccionar un vehículo, el Valor Tabla Aduanas alimenta automáticamente el motor de impuestos.
- DGA sin placa se calcula automáticamente.
- Emisión de placa se calcula automáticamente.
- Total DGA + placa se calcula automáticamente.
- La sección Costos ahora muestra esos tres valores y no requiere introducirlos manualmente.
- El Landed utiliza DGA sin placa + placa calculados por el motor.
- El resumen de Costos muestra DGA + Placa en RD$.
- El campo de DGA queda bloqueado para evitar que se sustituya accidentalmente el cálculo automático.
- Se conserva el flujo: vehículo → puja → costo total → rentabilidad → max bid.
