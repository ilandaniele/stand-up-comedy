---
name: comedy-writers-room
description: Use when helping write, punch up, or refine stand-up comedy, jokes, or humorous material — especially in Rioplatense Spanish (Arg/Uy), acidic and absurdist register. Runs a simulated writers room with subagents: one writes/revises, three audience personas react, then iterate.
---

# Comedy Writers Room (Rioplatense)

Escribí y puli chistes usando subagentes como sala de escritores. Un agente escribe (o reescribe), tres agentes reaccionan como personas distintas de público, y se itera en base a su feedback.

Adaptación rioplatense: el registro objetivo es **ácido + absurdo, en voseo (Arg/Uy)**. El público simulado es de un club / under porteño. Cuando el usuario ya tiene material propio, **preservá su voz** — esta sala mejora sus chistes, no los reemplaza por humor genérico.

## Proceso

### Paso 1: Despachar al escritor

Leé `writer-prompt.md` y usá esa plantilla para despachar un subagente.
- Reemplazá `[TOPIC]` con el tema (o pegá el material existente del usuario).
- En el primer borrador, omití la sección de revisión.
- Si el usuario ya tiene material, pasáselo entero e indicá que respete su voz.

### Paso 2: Despachar a los 3 miembros del público, en serie

Leé cada plantilla de público y despachá una a la vez:
1. `audience-enthusiast-prompt.md` (el Entusiasta)
2. `audience-skeptic-prompt.md` (el Escéptico)
3. `audience-overthinker-prompt.md` (el Sobrepensador)

Reemplazá `[JOKES]` con los chistes del escritor.

### Paso 3: Sintetizar el feedback

Leé lo que dijo cada persona. ¿Qué cerró? ¿Qué cayó muerto? ¿Qué confundió?
Cruzá con `joke-engineering` si querés diagnosticar *por qué* (estados H1–H6).

### Paso 4: Despachar al escritor de nuevo con el feedback

Usá `writer-prompt.md` otra vez, esta vez:
- Incluí la sección de revisión.
- Reemplazá `[FEEDBACK]` con la síntesis de reacciones.

### Paso 5: Repetir pasos 2–4 hasta que los chistes cierren

Pará cuando las personas reaccionen bien. Default: hasta 2–3 rondas; no la estires si ya no mejora.

### Paso 6: Presentar el material final al usuario

Incluí un resumen breve de cómo evolucionó: qué se cortó, qué surgió de la iteración, qué estado de joke-engineering se corrigió.

## Reglas críticas

- **Siempre usar la tool Task** — Nunca invocar el CLI `claude` por shell.
- **Despachar el público en serie** — Uno a la vez, para que cada reacción sea visible.
- **Incluir el feedback en las revisiones** — El escritor necesita saber qué arreglar.
- **Voseo y registro** — Todo el material y las reacciones van en español rioplatense, ácido y absurdo.
- **Preservar la voz del usuario** — Si trajo material propio, no lo neutralices.

## Créditos

Adaptado de `comedy-writers-room` de talsraviv (https://github.com/talsraviv/comedy-writers-room).
Pensado para usarse junto con la skill `joke-engineering` (diagnóstico estructural).
