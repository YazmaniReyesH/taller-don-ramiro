# Taller Don Ramiro

App web para que un taller mecánico pequeño permita a sus clientes ver el estado de su
coche y aprobar cotizaciones desde un enlace, con registro verificable (no repudio).

También avisa al cliente de forma proactiva en cada cambio de estado (aviso autogenerado
+ envío por WhatsApp de un toque) y permite confirmar la recolección del coche con horarios
predefinidos, todo con registro y línea de tiempo.

Construida con Spec Driven Development:
- `CLAUDE.md` — contexto persistente para el agente.
- `specs/aprobacion-cotizaciones.md` — especificación del feature de aprobación de cotizaciones.
- `specs/avisos-estado-recoleccion.md` — especificación de avisos de estado y confirmación de recolección.
- `.claude/skills/brand-design/SKILL.md` — sistema de diseño de marca.
- `index.html` — implementación generada por el agente a partir de las specs.