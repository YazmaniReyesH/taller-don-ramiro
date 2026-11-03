# Spec — Avisos automáticos de estado + confirmación de recolección

## 1. Definición del problema
Aunque el cliente ya puede consultar el estado por un enlace, sigue llamando varias veces
al día para preguntar si su coche está listo, porque nada le avisa cuando algo cambia:
tiene que acordarse de abrir el enlace. Cada llamada interrumpe al taller. Además, cuando
el coche queda listo, nadie coordina la recolección y el auto se queda ocupando espacio.
Se necesita avisar al cliente de forma proactiva en cada cambio de estado y coordinar la
recolección sin llamadas.

## 2. Diseño de la solución
- Al cambiar la etapa de un vehículo en la consola, el sistema genera automáticamente el
  aviso correspondiente a esa etapa (texto predefinido por etapa), lo registra con fecha y
  hora, y ofrece enviarlo al cliente con un toque (enlace de WhatsApp), sin redactar nada.
- La vista del cliente muestra una línea de tiempo de avisos (etapa + fecha y hora) para
  que vea el avance sin llamar, con un encabezado de estado grande y legible de un vistazo.
- Al llegar a "Listo para entrega", la vista del cliente ofrece "Confirmar recolección":
  el cliente elige un horario entre opciones predefinidas (hoy/mañana + franja) y confirma.
  La confirmación queda registrada con fecha y hora.
- La consola del mecánico muestra, por vehículo, si el cliente ya confirmó la recolección
  y para qué horario; si no, lo indica claramente.

Nota de alcance: en este prototipo sin backend, el "envío automático" se realiza como
aviso autogenerado + envío de un toque por WhatsApp + registro del aviso. El push real
requeriría backend; la mecánica queda demostrada.

## 3. Criterios de aceptación (verificables)
1. Al cambiar la etapa de un vehículo en la consola, el sistema genera el aviso de esa
   etapa y lo registra con fecha y hora; el aviso se puede enviar al cliente con un toque
   (WhatsApp) sin escribir nada.
2. La vista del cliente muestra la línea de tiempo de avisos en orden cronológico (etapa +
   fecha y hora) y un encabezado de estado actual legible de un vistazo.
3. Cuando el vehículo está "Listo para entrega", la vista del cliente permite confirmar la
   recolección eligiendo un horario de opciones predefinidas, y registra la confirmación
   con fecha y hora.
4. La consola muestra, por vehículo, el estado de la recolección: horario confirmado por el
   cliente, o "sin confirmar" si aún no responde.
5. Avisos y confirmación persisten (localStorage) y se conservan al recargar; el historial
   de avisos no es editable desde la interfaz.

## 4. Métricas de éxito
- Reducción de llamadas entrantes "¿ya está mi coche?" por taller/semana. Meta: −60% en 4
  semanas.
- % de clientes que abren al menos un aviso de estado. Meta: ≥70%.
- % de vehículos "Listo para entrega" con recolección confirmada por el cliente. Meta: ≥50%.
- Tiempo entre "Listo para entrega" y recolección efectiva. Meta: pasar de ~2 días a <1 día.
- Tiempo del mecánico avisando por WhatsApp uno por uno. Meta: ~0 (el aviso es de un toque).