---
name: brand-design
description: Sistema de diseño de marca para Taller Don Ramiro. Úsalo siempre que crees o modifiques cualquier UI de la app: define paleta, tipografía, componentes, tono y reglas visuales. No inventes colores ni tipografías fuera de este sistema.
---

# Diseño de marca — Taller Don Ramiro

## Personalidad
Taller de barrio: recio, confiable, directo. Industrial pero limpio, nada "app de banco".
Señal visual de la marca: cinta de precaución (ámbar sobre grafito).

## Paleta
- Grafito 900 #15171C — fondo de la consola del mecánico
- Grafito 800 #1C1F26 — tarjetas de la consola
- Ámbar #FFB020 — acento principal y acciones
- Ámbar profundo #E08A00 — alertas sobre fondo claro
- Papel #F4F5F7 y Blanco #FFFFFF — vista del cliente
- Tinta #1A1D23 — texto sobre claro
- Aprobado #1C9A57 (verde) · Rechazado #CE4040 (rojo)
Uso: consola = oscuro industrial; cliente = claro, limpio y confiable.

## Tipografía
- Barlow Condensed (600/700): títulos, placas de vehículo, montos.
- Barlow (400/500/600): cuerpo e interfaz.
- Jerarquía por tamaño y peso; sentence case; sin texto largo en mayúsculas.

## Componentes
- Botones de acción: alto mínimo 58px, radio ~13px, texto en Barlow Condensed.
  Primario = ámbar sobre grafito.
- Chips de estado por etapa, con los colores de arriba.
- Franja "hazard": repeating-linear-gradient ámbar/grafito a 135°. Es la firma visual;
  úsala una sola vez por pantalla (encabezado de la consola).
- Placa del vehículo: Barlow Condensed, letra espaciada, estilo matrícula.

## Accesibilidad y "manos sucias"
- Objetivos de toque grandes, poco tecleo, confirmaciones claras.
- Foco visible (outline ámbar), contraste AA, respetar prefers-reduced-motion.

## Voz
Español de México, frases cortas, voz activa. El botón dice lo que hace. Los errores
explican qué pasó y cómo seguir.

## Reglas
- Un solo elemento protagonista por pantalla; lo demás, callado.
- No repetir la franja hazard más de una vez por pantalla.
- No agregar sombras genéricas ni gradientes decorativos fuera de los definidos.

## Vista del cliente "estado primero" (evolución)
- Encabezado de estado a todo lo ancho, con color por etapa:
  en proceso = ámbar (#FFB020 sobre grafito), listo = verde (#1C9A57), espera = ámbar
  profundo (#E08A00). Titular en Barlow Condensed grande ("Tu Ranger está LISTO").
- Línea de tiempo de avisos como elemento principal: punto + etapa + fecha/hora.
- Bloque de "Confirmar recolección" prominente cuando el estado es "Listo para entrega".
- El objetivo es que el cliente entienda el estado en menos de 2 segundos, sin leer.