# Contexto del proyecto — Taller Don Ramiro

## Qué es
App web para un taller mecánico pequeño que permite al cliente consultar el estado de
su coche y aprobar o rechazar cotizaciones desde un enlace, sin llamar al taller.

## Usuarios y condiciones
- Mecánicos (4): usan el celular, casi siempre con las manos sucias. Interfaz móvil,
  botones grandes, mínimo tecleo, confirmaciones claras.
- Cliente: llega por un enlace. No instala app, no crea cuenta.
- Don Ramiro: supervisa los trabajos.

## Alcance
En alcance: estado del vehículo y aprobación de cotizaciones con registro.
Fuera de alcance (no construir): control de inventario (se lleva en Excel),
facturación/contabilidad, gestión compleja de usuarios y roles.

## Stack y convenciones técnicas
- HTML + CSS + JS vanilla, en un solo archivo autocontenido (index.html).
- Sin dependencias externas salvo Google Fonts.
- Mobile-first, interfaz en español de México.
- Objetivos de toque de 56px o más; poco tecleo.
- Accesibilidad: foco visible, contraste AA, respetar prefers-reduced-motion.
- Persistencia con localStorage envuelta en try/catch; la página debe funcionar con
  datos vacíos.
- Puntuación tipográfica en español (comillas " " y apóstrofo ').

## Marca
Sigue el sistema de .claude/skills/brand-design/SKILL.md. No inventes otra paleta ni
otras tipografías.

## Cómo trabajar (Spec Driven Development)
1. Lee la spec en specs/ antes de escribir código.
2. Implementa solo lo que la spec pide y respeta sus criterios de aceptación.
3. Si algo es ambiguo, pregunta antes de asumir.
4. Entrega en tandas pequeñas y haz una pausa para validación.
5. No agregues nada fuera del alcance.

## Idioma
Todo el texto visible para el usuario en español de México, sentence case, voz activa.
El botón dice lo que hace ("Aprobar este trabajo", no "Enviar").