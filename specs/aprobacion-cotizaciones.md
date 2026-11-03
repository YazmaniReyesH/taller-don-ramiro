# Spec — Aprobación de cotizaciones con registro verificable

## 1. Definición del problema
Cuando el taller detecta una reparación adicional, el trabajo se detiene hasta que el
cliente aprueba el costo por teléfono. Eso puede tardar días y, cuando el cliente
aprueba de palabra, después puede negar haberlo hecho. El taller necesita que el
cliente apruebe o rechace cotizaciones de forma rápida y que cada decisión quede
registrada de modo que no se pueda negar después (no repudio).

## 2. Diseño de la solución
Flujo:
- El mecánico crea una cotización (descripción, costo, foto opcional) desde su consola
  y la envía al cliente por un enlace de WhatsApp.
- El cliente abre su enlace privado (sin app, sin login), ve la cotización (descripción,
  costo, foto) y la aprueba o la rechaza.
- Antes de registrar, aparece una pantalla de confirmación que muestra el monto exacto
  y pide al cliente confirmar su identidad (confirma el nombre asociado al vehículo).
- Al confirmar, el sistema genera un registro inmodificable con: folio único, decisión,
  monto, nombre del cliente y fecha/hora.
- El registro se muestra al cliente (su comprobante) y al mecánico (su evidencia). Una
  vez tomada la decisión, los botones desaparecen y el registro no se puede editar.
- Si aprueba, el vehículo pasa a "En reparación" sin intervención del taller.

Modelo del registro (inmutable):
{ folio, cotizacionId, decision, monto, nombreCliente, timestamp }

## 3. Criterios de aceptación (verificables)
1. Dada una cotización pendiente, el cliente puede aprobarla o rechazarla desde el
   enlace sin instalar una app ni iniciar sesión.
2. La pantalla de confirmación muestra el monto exacto de la cotización y el nombre del
   cliente antes de registrar la decisión.
3. Al confirmar, se genera un registro con folio único, decisión, monto, nombre y
   fecha/hora, visible tanto para el cliente como para el mecánico.
4. Una vez tomada la decisión, la cotización deja de mostrar los botones de aprobar o
   rechazar, y al recargar la página el registro se conserva intacto (no editable desde
   la interfaz).
5. Al aprobar, el estado del vehículo cambia automáticamente a "En reparación" y la
   vista del cliente lo refleja sin que el taller haga nada más.